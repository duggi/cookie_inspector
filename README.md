# Cookie Inspector

The missing Cookie manager for the Chrome Browser. Adds a "cookies" panel in
the inspector panel. Use it to manage cookies in chrome.

Features:

- View, Add, Edit, Remove Cookies
- Live Reloading (No need to close and open the inspector when you change URLs)
- Export Cookies

Coming Soon:

- Import Cookies (SOON)

## Design

```
  +--------+      +--------+      +------------+
  | Client |<---->| Socket |<---->| Background |
  +--------+      +--------+      +------------+
```

### Client

The client is a Backbone.JS based application. The only difference is
that it doesn't use the callbacks associated with saving, removing, or
updating since it uses a system that functions like "websockets".
Instead, it listens for events coming from the background and takes care
of it appropriately.

### Socket

An object that mediates between the client and the background page.

### Background

The background page is the one that handles "server" side logic. Like
fetching cookies, adding, removing and so on. The background sends
messages to the client, and the client then either adds, removes, or
updates it to the list.

## Contributions

Icons by [Oxygen Team](http://www.oxygen-icons.org/)

## License

MIT
