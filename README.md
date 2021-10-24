# linkedin-Profile-Data-Fetch-Without-API-



Demo Link [https://linkedin-profile.codersalman.workers.dev/](https://linkedin-profile.codersalman.workers.dev/)

Linkedin Profile Fetch Plugin for Web application for fetching LinkedIn user profile Without API using Javascript 
---


# Return small Cloudflaer Page using Cloudflaer Workers

```js
addEventListener("fetch", (event) => {
  event.respondWith(
    handleRequest(event.request).catch(
      (err) => new Response(err.stack, { status: 500 })
    )
  );
});


 function handleRequest(request) {
  const { pathname } = new URL(request.url);

  if (pathname.startsWith("/api")) {
    return new Response(JSON.stringify({ pathname }), {
      headers: { "Content-Type": "application/json" },
    });
  }

  if (pathname.startsWith("/status")) {
    const httpStatusCode = Number(pathname.split("/")[2]);

    return Number.isInteger(httpStatusCode)
      ? fetch("https://http.cat/" + httpStatusCode)
      : new Response("That's not a valid HTTP status code.");
  }

  return fetch("https://linkedin-profile-data-fetch-without-api.pages.dev");
}



```
