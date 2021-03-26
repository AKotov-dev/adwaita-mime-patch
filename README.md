adwaita-mime-patch
---
Patch package that eliminates the overlap of mime-type icons in adwaita-icon-theme**  

In the version "adwaita-icon-theme"-3.38.0, the icons of the mime types "application-x-generic.png" overlap the newly created mime types from the "hicolor"
theme and puts empty icons instead of the mime icons of the application files. Only after manual intervention it becomes possible to see the real icons of
a particular mime type: `rename -v \.png \.bak $(find /usr/share/icons/Adwaita/*/mimetypes/ -name 'application-x-generic.*');  gtk-update-icon-cache -f /usr/share/icons/Adwaita/`  

A prime example is VirtualBox and virtual machine file extensions:  `*.vdi`, `*.vbox`, `*.vmdk`. This is just one example.
With the release of "adwaita-icon-theme"-3.38.0, the fault is present globally. Tested in Fedora 33 (Gnome/Mate), Solus 4.1 (Budgie/Mate/Gnome), Mageia-8 (all DE).
The latest version that works correctly - "adwaita-icon-theme"-3.37.2.

After installing this patch, the display of mime-type icons works correctly. After deleting the package, everything returns to its original state. That is, to quickly roll back when the problem is resolved.

GitLab: https://gitlab.gnome.org/GNOME/adwaita-icon-theme/-/issues/108  
Mageia Bugzilla – Bug 27644: https://bugs.mageia.org/show_bug.cgi?id=27644
