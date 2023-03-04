# Description
This lab has an unprotected admin panel. It's located at an unpredictable location, but the location is disclosed somewhere in the application.

Solve the lab by accessing the admin panel, and using it to delete the user `carlos`.

# Process
I started out by inspecting the source code of the homepage. Here, I quickly found a short script:
```
var isAdmin = false;
if (isAdmin) {
   var topLinksTag = document.getElementsByClassName("top-links")[0];
   var adminPanelTag = document.createElement('a');
   adminPanelTag.setAttribute('href', '/admin-7ymeia');
   adminPanelTag.innerText = 'Admin panel';
   topLinksTag.append(adminPanelTag);
   var pTag = document.createElement('p');
   pTag.innerText = '|';
   topLinksTag.appendChild(pTag);
}
```
The purpose of this code was pretty easy to understand. If the user is an administrator, an item is added to the top menu that allows them to navigate to the admin panel. Fortunately, the code also discloses the link to the admin panel, `/admin-7ymeia`.

Navigating to this URL takes me to the admin panel. Once there, I can delete the user `carlos` and solve the lab.