## Enable XDG Desktop Portal by default

This change adds the `--xdg-desktop-portal=default` flag to the Flatpak finish-args.

### Why this is needed:
Running ONLYOFFICE with this flag forces the application to use the native system file picker and desktop portal integrations instead of fallback dialogs. 

### Manual verification:
The fix was tested locally by running:
flatpak run org.onlyoffice.desktopeditors --xdg-desktop-portal=default

And by appending the flag to the desktop file launcher:
Exec=/usr/bin/flatpak run --branch=stable --arch=x86_64 --command=desktopeditors --file-forwarding org.onlyoffice.desktopeditors @@u %U @@ --xdg-desktop-portal=default
