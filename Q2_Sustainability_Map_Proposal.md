# Q2. Interactive IIT Bombay Sustainability Map

**What I want to build.** A map of the IITB campus where every sustainability initiative is shown as a pin. Click a pin and a card opens with everything about that project: what it is, who runs it, a photo, and how to find it. Filters at the top let you see only one category at a time (energy projects, e-waste points, etc.), and a search box finds a project by name.

**Tools and platforms.** React for the website, Leaflet.js for the map (it is open-source and works without an API key or billing, unlike Google Maps), and Firebase Firestore to store the project data. Firebase Hosting or GitHub Pages for deployment.

**How it would work.** All project data lives in Firestore. Each project is one entry with its name, coordinates, category, description, and photo. When the page loads, the site reads from Firestore and Leaflet drops a pin for each one on the campus map. Clicking a pin opens its card. Storing data this way means anyone in SusCell can add a new project later by just adding an entry, no coding needed.

**Major steps.** Design the layout, set up Leaflet with a campus image overlay, connect Firestore, render the pins, add the filters, search, and click-cards, make it work on mobile, deploy, and seed it with the real campus projects.

**Extra ideas.** A "near me" button that highlights the closest projects using the phone's location. A form for students to suggest new spots, which goes into Firestore as a pending entry SusCell can review. QR codes stuck at each physical site (for example on the biogas plant wall) that open that project's card directly when scanned.
