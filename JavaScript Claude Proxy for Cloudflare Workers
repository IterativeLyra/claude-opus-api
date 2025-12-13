export default {
  async fetch(request, env) {
    const url = "https://chat-api.antigravity.space/api/chat";

    const body = await request.text();

    const headers = {
      "Authorization": `Bearer ${env.ANTIGRAVITY_API_KEY}`,
      "Content-Type": "application/json"
    };

    const forwarded = await fetch(url, {
      method: "POST",
      headers,
      body
    });

    return new Response(forwarded.body, {
      status: forwarded.status,
      headers: { "Content-Type": "application/json" }
    });
  }
}
