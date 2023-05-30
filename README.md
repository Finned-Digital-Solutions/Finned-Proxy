# Finned-Proxy
> A simple Cloudflare worker for scraping. Comes with authentication out of the box.

## Features
- Simple setup on free Cloudflare worker.
- Supports auth by API key out of the box.
- Returns content quickly with underrstandable messages.
- Variety of use cases, from obscuring IP address to bypassing CORS.

## Configuration
1. Make a ``wrangler.toml`` file in the project root.
2. Add the below content:
  ```toml
name = "finned-proxy"
main = "src/index.js"
compatibility_date = "2023-02-27"

[vars]
API_KEY = "<a secure string here>"
  ```
  Note that ``API_KEY`` is a random string that you make yourself. This will be the authentication you need to pass to the app in order to make requests.
3. Save the file

## Starting
1. Start the application.
  ``npm start``
2. If you have not already, you will be prompted to sign in to Cloudflare.
3. Test the application: ``curl "https://finned-proxy.npiqwxyai.workers.dev/?auth=<api key>&url=<url to retrieve>"``
4. Publish the site to Cloudflare: ``npx wrangler publish``

## License
MIT
