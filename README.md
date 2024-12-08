# portfolio-website

To create a personal portfolio website with three pages (Home, About, and Contact) using Custom CSS, follow the steps below. This approach will give you a clean, responsive portfolio that highlights your skills and projects.

1. Set Up Your Project:
Start by setting up a new React project for your portfolio website.

bash
Copy code
npx create-react-app portfolio-website
cd portfolio-website
npm start
2. Install Dependencies:
If you plan to use React Router for navigation between pages, install it using:

bash
Copy code
npm install react-router-dom
3. Folder Structure:
Create a structure to organize your components and pages.

src/
components/: For common elements like Navbar, Footer.
pages/: For your specific pages (Home, About, Contact).
styles/: For custom CSS files.
4. Create Pages and Components:
You’ll need three pages (Home, About, Contact) and some reusable components (Navbar, Footer).

Navbar Component (src/components/Navbar.js):
jsx
Copy code
import React from 'react';
import { Link } from 'react-router-dom';

const Navbar = () => {
    return (
        <nav>
            <ul>
                <li><Link to="/">Home</Link></li>
                <li><Link to="/about">About</Link></li>
                <li><Link to="/contact">Contact</Link></li>
            </ul>
        </nav>
    );
};

export default Navbar;
Home Page (src/pages/Home.js):
jsx
Copy code
import React from 'react';

const Home = () => {
    return (
        <div className="home">
            <h1>Welcome to My Portfolio</h1>
            <p>I'm a Web Developer passionate about creating amazing websites!</p>
        </div>
    );
};

export default Home;
About Page (src/pages/About.js):
jsx
Copy code
import React from 'react';

const About = () => {
    return (
        <div className="about">
            <h1>About Me</h1>
            <p>Hi, I'm [Your Name]. I specialize in front-end development and have experience with React, JavaScript, and more.</p>
        </div>
    );
};

export default About;
Contact Page (src/pages/Contact.js):
jsx
Copy code
import React from 'react';

const Contact = () => {
    return (
        <div className="contact">
            <h1>Contact Me</h1>
            <form>
                <input type="text" placeholder="Your Name" />
                <input type="email" placeholder="Your Email" />
                <textarea placeholder="Your Message"></textarea>
                <button type="submit">Send Message</button>
            </form>
        </div>
    );
};

export default Contact;
5. Routing Setup:
In your src/App.js, set up React Router to navigate between the pages.

jsx
Copy code
import React from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import Navbar from './components/Navbar';
import Home from './pages/Home';
import About from './pages/About';
import Contact from './pages/Contact';

import './styles.css';  // Custom CSS

function App() {
    return (
        <Router>
            <Navbar />
            <Routes>
                <Route path="/" element={<Home />} />
                <Route path="/about" element={<About />} />
                <Route path="/contact" element={<Contact />} />
            </Routes>
        </Router>
    );
}

export default App;
6. Custom CSS (src/styles/styles.css):
Now, let's design the layout and style the website using custom CSS.

Example CSS:
css
Copy code
/* Global Styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
}

h1 {
    font-size: 2rem;
    color: #333;
}

ul {
    list-style-type: none;
}

a {
    text-decoration: none;
    color: inherit;
}

nav {
    background-color: #333;
    padding: 10px;
}

nav ul {
    display: flex;
    justify-content: center;
    gap: 20px;
}

nav ul li {
    display: inline;
}

nav ul li a {
    color: white;
    font-size: 1.2rem;
}

/* Home Page */
.home {
    text-align: center;
    padding: 50px;
}

.home h1 {
    font-size: 3rem;
    margin-bottom: 20px;
}

.home p {
    font-size: 1.2rem;
}

/* About Page */
.about {
    padding: 50px;
    text-align: center;
}

.about h1 {
    font-size: 2.5rem;
    margin-bottom: 20px;
}

.about p {
    font-size: 1.1rem;
    line-height: 1.6;
}

/* Contact Page */
.contact {
    padding: 50px;
    text-align: center;
}

.contact form {
    display: flex;
    flex-direction: column;
    gap: 15px;
    max-width: 400px;
    margin: 0 auto;
}

.contact input, .contact textarea {
    padding: 10px;
    font-size: 1rem;
    width: 100%;
    border: 1px solid #ccc;
    border-radius: 5px;
}

.contact button {
    padding: 10px;
    background-color: #333;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

.contact button:hover {
    background-color: #555;
}

/* Responsive Design */
@media (max-width: 768px) {
    .home h1 {
        font-size: 2rem;
    }

    .about h1 {
        font-size: 2rem;
    }

    .contact form {
        width: 90%;
    }
}
7. Run the Project:
Now, run your React app:

bash
Copy code
npm start
This will start the server and you can view your portfolio at http://localhost:3000.

8. Additional Enhancements (Optional):
Animations: Use CSS animations to animate elements when the page loads.
More Pages: Add a "Projects" page to showcase your work or a "Blog" page if you want to write about your experience.
Form Handling: Set up a backend service or use services like Formspree or EmailJS to handle form submissions.
Icons and Images: Add images and icons (e.g., social media icons) to enhance the design.
Summary:
You now have a personal portfolio website with:

Three pages: Home, About, Contact.
Custom CSS for styling and layout, including a responsive design.
React Router for page navigation.
