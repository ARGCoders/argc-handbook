# Tooling

ARGC runs on a defined stack: Next.js for the platform frontend and proxy layer, PocketBase for the data backend, GitHub for all code and handbook content. Tools are chosen for reliability and maintainability, not novelty. The frontend never calls PocketBase directly — all requests go through the Next.js backend layer.
