self.addEventListener('install', (event) => {
    event.waitUntil(
        caches.open('shadowclaude-v1').then((cache) => {
            return cache.addAll([
                '/index.html',
                '/manifest.json',
                '/icon.png',
                'https://js.puter.com/v2/'
            ]);
        })
    );
});

self.addEventListener('fetch', (event) => {
    event.respondWith(
        caches.match(event.request).then((response) => {
            return response || fetch(event.request);
        })
    );
});