# `Install React and React DOM`
```jsx
npm install react react-dom
```

# `Install Chakra UI and Emotion`
```jsx
npm install @chakra-ui/react @emotion/react @emotion/styled
```

# `Install font source`
```jsx
npm install @fontsource/poppins
```

# `Install React Three Fiber and Drei`
```jsx
npm install @react-three/fiber @react-three/drei
```

# `Install additional dependencies`
```jsx

npm install autoprefixer framer-motion keep-react phosphor-react postcss react-icons react-slick react-typed slick-carousel swiper tailwindcss three

```



# Portfolio Website

This is a simple yet elegant portfolio website built using **React**, **Keep React** (UI Library), and **Tailwind CSS**. The project includes responsive components, dynamic text writing, social links, and several modern design elements for a sleek and visually appealing experience.

## Features

- Responsive layout for various screen sizes.
- Portfolio image component that scales responsively.
- Modern and sleek UI using **Tailwind CSS**.
- Dynamic text writer for showcasing titles and roles.
- Downloadable CV option and social media links with hover effects.
- Easily customizable components for personal preferences.

---

## Components

### 1. `Navbar` Component

The `Navbar` component ensures a seamless navigation experience, with a professional and modern design. This component utilizes the **Keep React UI Library** and **Tailwind CSS** for building a responsive and clean user interface. It also features an avatar dropdown for easy navigation on smaller screens.

Key elements include:

- **NavbarBrand**: Displays the website's logo.
- **NavbarList**: Contains navigation items such as "Home", "Skills", "Projects", etc.
- **Dropdown Avatar**: Displays the user's profile picture with an accessible dropdown menu.
- **NavbarCollapse**: Ensures proper navigation and UI collapse functionality on smaller screens.

```jsx
//Navbar1.jsx
import {
  Avatar,
  Dropdown,
  DropdownAction,
  DropdownContent,
  DropdownItem,
  DropdownList,
  Navbar,
  NavbarBrand,
  NavbarCollapse,
  NavbarCollapseBtn,
  NavbarContainer,
  NavbarItem,
  NavbarList,
  AvatarImage,
} from "keep-react";

import profile from "../images/Profile.jpeg";
import logo from "../images/Html.png";
// The Navbar1 component sets up the navigation bar, with a logo and navigation links
// Dropdown Avatar is used to show profile options for smaller screens.

export const Navbar1 = () => {
  return (
    <Navbar className="px-5 bg-gradient-to-t from-black to-gray-600">
      {/* Navbar container for logo and navigation */}
      <NavbarContainer>
        <NavbarBrand>
          <img src={logo} alt="Logo" className="w-[50px] h-[50px]" />
        </NavbarBrand>

        {/* Navigation Links */}
        <NavbarList>
          <NavbarItem className="text-white font-semibold">Home</NavbarItem>
          <NavbarItem className="text-white font-semibold">Skills</NavbarItem>
          <NavbarItem className="text-white font-semibold">Projects</NavbarItem>
          <NavbarItem className="text-white font-semibold">Services</NavbarItem>
          <NavbarItem className="text-white font-semibold">About</NavbarItem>
          <NavbarItem className="text-white font-semibold">Contact</NavbarItem>
        </NavbarList>

        {/* Dropdown Avatar for user profile on smaller screens */}
        <NavbarList>
          <Dropdown placement="bottom-end">
            <DropdownAction asChild>
              <Avatar>
                <AvatarImage src={profile} />
              </Avatar>
            </DropdownAction>
            <DropdownContent className="border border-metal-100">
              <DropdownList>
                <DropdownItem className="text-white font-semibold">Home</DropdownItem>
                <DropdownItem className="text-white font-semibold">Skills</DropdownItem>
                <DropdownItem className="text-white font-semibold">Projects</DropdownItem>
                <DropdownItem className="text-white font-semibold">Services</DropdownItem>
                <DropdownItem className="text-white font-semibold">About</DropdownItem>
                <DropdownItem className="text-white font-semibold">Contact</DropdownItem>
              </DropdownList>
            </DropdownContent>
          </Dropdown>
        </NavbarList>

        {/* Collapse button for mobile view */}
        <NavbarCollapseBtn />
        <NavbarCollapse>
          <NavbarItem>Home</NavbarItem>
          <NavbarItem>Skills</NavbarItem>
          <NavbarItem>Projects</NavbarItem>
          <NavbarItem>Services</NavbarItem>
          <NavbarItem>About</NavbarItem>
          <NavbarItem>Contact</NavbarItem>
        </NavbarCollapse>
      </NavbarContainer>
    </Navbar>
  );
};

```

### 2. `TextWriter` Component

The `TextWriter` component is designed to introduce the developer by dynamically displaying various roles or titles. It uses **ReactTyped** to create a typing animation, and **Framer Motion** for smooth animations when transitioning elements onto the screen. Social media links and a downloadable CV button are included to enhance interactivity.

#### Key Features:

- **Dynamic Text**: The component uses `ReactTyped` to cycle through different roles (e.g., Web Developer, JavaScript Enthusiast).
- **Download CV Button**: Allows users to download your CV in a sleek button with hover animations.
- **Social Links**: Includes LinkedIn, GitHub, Twitter, and email icons for easy navigation to your profiles.

#### Code Example:

```jsx
//TextWriter.jsx
import React from "react";
import ReactTyped from "react-typed";
import { FaLinkedin, FaGithub, FaTwitter, FaEnvelope } from "react-icons/fa"; // Social Media Icons
import { motion } from "framer-motion"; // Animation library

// The TextWriter component displays the user's name and their roles dynamically
// ReactTyped is used to create the typing effect for different roles

const TextWriter = ({ yourname = "Arun Kumar" }) => {
  return (
    <div className="flex flex-col items-center justify-center min-h-screen bg-black text-white">
      
      {/* Motion.div adds smooth entry animations for the text */}
      <motion.div
        className="text-center my-10 w-full max-w-4xl mx-auto"
        initial={{ opacity: 0, scale: 0.8 }}
        animate={{ opacity: 1, scale: 1 }}
        transition={{ duration: 1 }}
      >
        {/* User's Name */}
        <h1 className="text-5xl font-extrabold mb-4">
          Hi, I'm {yourname}
        </h1>

        {/* Dynamic Typing Animation */}
        <h2 className="text-2xl">
          <ReactTyped
            strings={[
              "Web Developer 💻",
              "JavaScript Enthusiast 🚀",
              "React Developer ⚛️",
              "Tech Blogger ✍️",
            ]}
            typeSpeed={40}
            backSpeed={50}
            loop
          />
        </h2>
      </motion.div>

      {/* Download CV Button */}
      <motion.div
        className="mt-8"
        initial={{ y: 20, opacity: 0 }}
        animate={{ y: 0, opacity: 1 }}
        transition={{ delay: 0.5, duration: 0.8 }}
      >
        <a
          href="path-to-your-cv.pdf"
          download="ArunKumar-CV"
          className="btn btn-primary bg-blue-500 text-white px-6 py-3 rounded-lg shadow-lg hover:bg-blue-600 transition duration-300 transform hover:scale-105"
        >
          Download CV
        </a>
      </motion.div>

      {/* Social Media Links */}
      <motion.div
        className="flex justify-center mt-8 space-x-6"
        initial={{ y: 20, opacity: 0 }}
        animate={{ y: 0, opacity: 1 }}
        transition={{ delay: 0.7, duration: 0.8 }}
      >
        {/* LinkedIn Link */}
        <a
          href="https://linkedin.com/in/your-profile"
          target="_blank"
          rel="noopener noreferrer"
          className="text-4xl text-blue-700 hover:text-blue-900 transition duration-300"
        >
          <FaLinkedin />
        </a>
        {/* GitHub Link */}
        <a
          href="https://github.com/your-profile"
          target="_blank"
          rel="noopener noreferrer"
          className="text-4xl text-gray-800 hover:text-black transition duration-300"
        >
          <FaGithub />
        </a>
        {/* Twitter Link */}
        <a
          href="https://twitter.com/your-profile"
          target="_blank"
          rel="noopener noreferrer"
          className="text-4xl text-blue-400 hover:text-blue-600 transition duration-300"
        >
          <FaTwitter />
        </a>
        {/* Email Link */}
        <a
          href="mailto:your-email@example.com"
          className="text-4xl text-red-600 hover:text-red-800 transition duration-300"
        >
          <FaEnvelope />
        </a>
      </motion.div>
    </div>
  );
};

export default TextWriter;


```

### 3. `PortfolioImage` Component

The `PortfolioImage` component is designed to display a circular portfolio image. This component utilizes responsive design principles to ensure that the image looks great on various screen sizes. 

#### Key Features:

- **Circular Image**: The image is displayed in a rounded format using Tailwind CSS classes.
- **Responsive Design**: The image size adapts according to the screen size, providing an optimal viewing experience on all devices.

#### Code Example:

```jsx
//PortfolioImage.jsx
import React from "react"; // Importing React library to create the component
import image from '../images/portfolio.webp';

const PortfolioImage = () => {
  return (
    // Container for the image with flexbox and rounded shape
    <div className="rounded-full flex justify-center items-center max-w-full">
      <img
        // Styling the image to be circular and responsive
        className="rounded-full w-48 h-48 sm:w-60 sm:h-60 lg:w-72 lg:h-72 xl:w-80 xl:h-80 object-cover"
        src={image} // Source of the image, defaults to the specified path
        alt="Portfolio" // Alt text for accessibility
      />
    </div>
  );
};

export default PortfolioImage; // Exporting the component for use in other parts of the application

```

### Summary of Code:

- **Import Statement**: Imports the React library necessary for creating the component.
- **Component Definition**: Defines the `PortfolioImage` component, which accepts an `image` prop with a default value.
- **Container Div**: A `div` is used to center the image and apply a rounded shape.
- **Image Element**: The `img` element applies Tailwind CSS classes for responsiveness and circular styling.
- **Export Statement**: Exports the `PortfolioImage` component for use in other parts of the portfolio website.




### 4. `Home` Component

The `Home` component serves as the main landing section of the portfolio website, combining both the `TextWriter` and `PortfolioImage` components. This layout is responsive, ensuring that both sections are displayed elegantly on various screen sizes.

#### Key Features:

- **Responsive Layout**: Utilizes a flexbox layout that adjusts to different screen sizes, ensuring a great user experience.
- **Separation of Concerns**: Integrates the `TextWriter` and `PortfolioImage` components for a clean structure.

#### Code Example:

```jsx
//Home.jsx
import React from "react"; // Importing React library to create the component
import TextWriter from "./TextWriter"; // Importing the TextWriter component
import PortfolioImage from "./PortfolioImage"; // Importing the PortfolioImage component

const Home = () => {
  return (
    // Container for the Home component, using flexbox for layout
    <div className="flex flex-col justify-center items-center lg:flex-row flex-wrap bg-[#527385]">
      {/* Left Side: TextWriter Component */}
      <div className="left w-full lg:w-1/2 flex justify-center items-center p-4">
        <TextWriter className="w-full h-auto" /> {/* Render the TextWriter component */}
      </div>
      {/* END */}
      {/* Right Side: PortfolioImage Component */}
      <div className="right w-full lg:w-1/2 flex justify-center items-center p-4">
        <PortfolioImage /> {/* Render the PortfolioImage component */}
      </div>
      {/* END */}
    </div>
  );
};

export default Home; // Exporting the Home component for use in other parts of the application

```


### Summary of Code:

- **Import Statements**: Imports the React library and the `TextWriter` and `PortfolioImage` components.
- **Component Definition**: Defines the `Home` component, which encapsulates the layout for the homepage.
- **Container Div**: Uses a flexbox layout to arrange child components in a column on small screens and in a row on larger screens.
- **Left Side**: Contains the `TextWriter` component, centered within its flex container.
- **Right Side**: Contains the `PortfolioImage` component, also centered within its flex container.
- **Export Statement**: Exports the `Home` component for use in other parts of the portfolio website.


### 5. `Heading` Component

The `Heading` component serves as a dynamic and visually engaging title for sections of the portfolio website. It utilizes Framer Motion for animations, creating an appealing user experience as users scroll.

#### Key Features:

- **Animated Scroll Effects**: The heading slides in from above, fades in, and gently zooms as the user scrolls down the page.
- **Hover Effect**: Provides a subtle scaling effect when the user hovers over the heading.
- **Customizable Title**: Accepts a `title` prop to dynamically set the heading text.

#### Code Example:

```jsx
// Heading.jsx
import React from 'react'; // Importing React library to create the component
import { motion, useScroll, useTransform } from 'framer-motion'; // Importing motion and hooks for scroll-based animations

const Heading = ({ title = 'Title' }) => {
    const { scrollY } = useScroll(); // Hook to track vertical scroll position
    // Transform scroll position to create a slide-in effect
    const y = useTransform(scrollY, [0, 100], [-50, 0]); // Slide in from above
    const opacity = useTransform(scrollY, [0, 100], [0, 1]); // Fade in effect
    const scale = useTransform(scrollY, [0, 100], [0.9, 1]); // Scale effect for a gentle zoom

    return (
        <div className="bg-gradient-to-r from-pink-200 via-white to-pink-200 p-1 flex justify-center items-center my-4">
            <motion.h1
                className="font-bold text-4xl uppercase tracking-widest"
                style={{ y, opacity, scale }} // Applying animated styles based on scroll
                initial={{ y: -100, opacity: 0 }} // Initial state for more dramatic entry
                animate={{ y: 0, opacity: 1, transition: { duration: 0.5, ease: "easeOut" } }} // Animate to visible
                whileHover={{ scale: 1.05 }} // Slight zoom on hover
            >
                {title} {/* Render the title prop */}
            </motion.h1>
        </div>
    );
};

export default Heading; // Exporting the Heading component for use in other parts of the application

```

### Summary of Code:

- **Import Statements**: Imports the React library and necessary hooks from Framer Motion.
- **Component Definition**: Defines the `Heading` component, which takes a `title` prop.
- **Scroll Hooks**: Utilizes `useScroll` to track the user's scroll position and `useTransform` to create animated effects based on that position.
- **Transformations**: Defines how the heading's position, opacity, and scale change as the user scrolls down the page.
- **Container Div**: Wraps the heading in a div with a gradient background and flexbox styling for centering.
- **Motion Element**: Uses the `motion.h1` to create an animated heading that responds to scroll and hover actions.
- **Export Statement**: Exports the `Heading` component for use in other parts of the portfolio website.


### 6. `Card1` Component

The `Card1` component is a reusable UI card designed to display a title and a description. It utilizes components from the `keep-react` library to create a clean and modern card layout.

#### Key Features:

- **Reusable Component**: Can be used multiple times with different titles and descriptions.
- **Customizable Title and Description**: Accepts `title` and `description` props to dynamically set the card content.
- **Styling**: Styled with a maximum width for responsive design.

#### Code Example:

```jsx
//Card1.jsx
import { Card, CardContent, CardDescription, CardTitle } from "keep-react"; // Importing Card components from the keep-react library

// Defining the Card1 component with destructured props for title and description
export const Card1 = ({ description = "Description", title = "Title" }) => {
  return (
    <Card className="max-w-md"> {/* Card component with a maximum width */}
      <CardContent> {/* Container for card content */}
        <CardTitle>{title}</CardTitle> {/* Displaying the title prop */}
        <CardDescription>{description}</CardDescription> {/* Displaying the description prop */}
      </CardContent>
    </Card>
  );
}; // Exporting the Card1 component for use in other parts of the application
```

### Summary of Code:

- **Import Statements**: Imports necessary components (`Card`, `CardContent`, `CardDescription`, `CardTitle`) from the `keep-react` library.
- **Component Definition**: Defines the `Card1` component, which takes `title` and `description` props with default values.
- **Card Structure**: Uses the `Card` component to create the card structure, with a maximum width for better responsiveness.
- **Content Display**: Inside the `CardContent`, it renders the `CardTitle` and `CardDescription` components using the provided props.
- **Export Statement**: Exports the `Card1` component for use in other parts of the application.



### 7. `Card2` Component

The `Card2` component is a customizable card that includes an image, title, description, and a button. It leverages components from the `keep-react` library to create a visually appealing card layout.

#### Key Features:

- **Customizable Image**: Accepts an `image` prop to display a custom image in the card.
- **Dynamic Title and Description**: Props for `title` and `description` allow for flexible content.
- **Interactive Button**: Includes a button for user interaction.

#### Code Example:

```jsx
//Card2.jsx
import "../index.css"; // Importing CSS styles
import {
  Button,
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "keep-react"; // Importing Card components from the keep-react library
import images from "../images/Html.png"
// Defining the Card2 component with destructured props for title, description, and image
export const Card2 = ({
  description = "Description", // Default description
  title = "Title", // Default title
  image = {images}, // Default image source
  ...props // Rest of the props
}) => {
  return (
    <>
      <Card> {/* Main card component */}
        <CardHeader className="flex justify-center items-center p-5"> {/* Card header with flex styling for centering */}
          <img
            src={image} // Using the image prop to set the image source
            className="rounded-t-xl w-[100px] h-[100px]" // Styling for image with rounded corners
            alt="image" // Alt text for accessibility
          />
        </CardHeader>
        <CardContent className="space-y-3"> {/* Container for the main content of the card */}
          <CardTitle>{title}</CardTitle> {/* Displaying the title prop */}
          <CardDescription>{description}</CardDescription> {/* Displaying the description prop */}
          <Button>Check Now</Button> {/* Button for user interaction */}
        </CardContent>
      </Card>
    </>
  );
}; // Exporting the Card2 component for use in other parts of the application

```

### Summary of Code:

- **Import Statements**: Imports the necessary CSS and components from the `keep-react` library.
- **Component Definition**: Defines the `Card2` component, accepting `description`, `title`, and `image` props with default values.
- **Card Structure**: Uses the `Card` component to create the card, with a header for the image and content for the title, description, and button.
- **Image Handling**: The image is displayed in the `CardHeader`, styled with rounded corners and specific dimensions.
- **Content Display**: Inside the `CardContent`, it renders the `CardTitle` and `CardDescription` components using the provided props, followed by a button labeled "Check Now."
- **Export Statement**: Exports the `Card2` component for use in other parts of the application.


### 8. `Card3` Component

The `Card3` component is a responsive card that showcases a project with an image, title, description, and a link to the project. It utilizes React Icons for an interactive link icon.

#### Key Features:

- **Image Display**: Displays an image related to the project.
- **Dynamic Content**: Accepts props for the title, description, and project link.
- **Interactive Link**: Includes a clickable link that opens in a new tab.

#### Code Example:

```jsx
// Card3.jsx
import React from "react"; // Importing React
import { FaLink } from "react-icons/fa"; // Importing the link icon from react-icons
import "../index.css"; // Importing CSS styles

// Defining the Card3 component with destructured props for title, description, image, and projectLink
const Card3 = ({ title, description, image, projectLink }) => {
  return (
    <div className="max-w-sm rounded-lg overflow-hidden shadow-lg m-4 transform transition-transform hover:scale-105 bg-white"> {/* Main card container with styling */}
      <img className="w-full h-48 object-cover p-3" src={image} alt={title} /> {/* Project image with styling */}
      <div className="px-6 py-4"> {/* Container for card content */}
        <div className="font-bold text-xl mb-2 text-metal-900">{title}</div> {/* Title with bold styling */}
        <p className="text-gray-600 text-base mb-4">{description}</p> {/* Project description */}
        <a
          href={projectLink} // Link to the project
          target="_blank" // Opens link in a new tab
          rel="noopener noreferrer" // Security measure to prevent security vulnerabilities
          className="flex items-center text-blue-500 hover:text-blue-700 font-bold" // Styling for the link
        >
          <FaLink className="mr-2" /> {/* Link icon with margin */}
        </a>
      </div>
    </div>
  );
};

export default Card3; // Exporting the Card3 component for use in other parts of the application


```

### Summary of Code:

- **Import Statements**: Imports React and the `FaLink` icon from the `react-icons` library, along with the necessary CSS.
- **Component Definition**: Defines the `Card3` component, which takes in `title`, `description`, `image`, and `projectLink` as props.
- **Card Structure**: The main container uses utility classes for styling and responsiveness, including a hover effect for scaling.
- **Image Handling**: The project image is displayed at the top of the card with specific dimensions and padding.
- **Content Display**: The card content section displays the title and description, formatted with specific text styles.
- **Link to Project**: A link is provided to the project, styled with a color that changes on hover, including an icon for visual representation.
- **Export Statement**: Exports the `Card3` component for use in other parts of the application.


### 9. `Card4` Component

The `Card4` component is a dynamic card designed to display information with a visual icon, title, and description. It incorporates animations using Framer Motion for a more interactive user experience.

#### Key Features:

- **Animated Entry**: Fades in and slides up when rendered.
- **Interactive Hover Effects**: Includes scaling and rotation animations on hover.
- **Gradient Background**: Features a visually appealing gradient background.

#### Code Example:

```jsx
// Card4.jsx
import { motion } from "framer-motion"; // Importing motion for animations
import {
  FaCode,
  FaChartLine,
  FaMobileAlt,
  FaSearch,
  FaProjectDiagram,
  FaShoppingCart,
} from "react-icons/fa"; // Importing various icons from react-icons

// Defining the Card4 component with destructured props for title, description, and icon
const Card4 = ({ title, description, icon }) => {
  return (
    <motion.div
      className="bg-white rounded-lg shadow-lg transition-transform duration-300 transform hover:scale-105 hover:shadow-2xl" // Main card container with styling
      initial={{ opacity: 0, y: 20 }} // Initial state for the fade-in and slide-up effect
      animate={{ opacity: 1, y: 0 }} // Animate to visible state
      transition={{ duration: 0.5 }} // Duration of the animation
      whileHover={{ rotateY: 10 }} // Slightly rotate on hover for interaction
    >
      <div className="p-6 bg-gradient-to-r from-pink-200 via-white to-pink-200 rounded-t-lg flex items-center"> {/* Header section with gradient background */}
        <motion.div
          className="text-3xl mr-4" // Icon styling with margin
          whileHover={{ scale: 1.2 }} // Animate icon scaling on hover
        >
          {icon} {/* Display the icon passed as a prop */}
        </motion.div>
        <h1 className="text-2xl font-semibold">{title}</h1> {/* Title of the card */}
      </div>
      <div className="p-4"> {/* Container for card content */}
        <p className="text-gray-700">{description}</p> {/* Description of the card */}
      </div>
    </motion.div>
  );
};

export default Card4; // Exporting the Card4 component for use in other parts of the application

```

### Summary of Code:

- **Import Statements**: Imports `motion` from Framer Motion for animations and various icons from the `react-icons` library.
- **Component Definition**: Defines the `Card4` component, which takes in `title`, `description`, and `icon` as props.
- **Card Structure**: The main container uses utility classes for styling, transitions, and hover effects to enhance user interaction.
- **Animation**: The card fades in and slides up on render, with a hover effect that slightly rotates the card.
- **Header Section**: Contains a gradient background, an animated icon, and the title of the card.
- **Content Section**: Displays the description of the card.
- **Export Statement**: Exports the `Card4` component for use in other parts of the application.

### 10. `Skills` Component

The `Skills` component is designed to showcase various skills and relevant projects. It consists of two main sections: a top section displaying specific technical skills and a bottom section featuring links to important profiles and resources. Each skill is represented by a card that provides a title, description, and an associated image.

#### Key Features:

- **Responsive Design**: The layout adjusts for various screen sizes using Flexbox.
- **Gradient Backgrounds**: Each card features a visually appealing gradient background.
- **Icons for Profiles**: Includes recognizable icons for GitHub, LinkedIn, Vercel, and personal portfolios.

#### Code Example:

```jsx
// Skills.jsx
import { FaGithub, FaLinkedin, FaUserCircle } from "react-icons/fa"; // Importing social media icons
import { RxVercelLogo } from "react-icons/rx"; // Importing Vercel logo
import "react"; // Importing React (though not explicitly needed)
import { Card1 } from "./Card1"; // Importing Card1 component
import { Card2 } from "./Card2"; // Importing Card2 component
import Html from "../images/Html.png"
import CSS from "../images/CSS.png"
import JS from "../images/Javascript.png"
import Node from "../images/Nodejs.png"
import React from "../images/React.png"
import Python from "../images/Python.png"
import SQL from "../images/SQL.png"
import Cpp from "../images/C++.png"

// Defining the Skills component
export const Skills = () => {
  return (
    <div className="flex flex-col gap-5 mt-5 p-5"> {/* Container for the entire Skills section */}
      {/* Top Section Start */}
      <div className="basis-full rounded-xl border border-dashed p-10 bg-gradient-to-r from-slate-300 via-white to-pink-100 flex flex-wrap gap-9 justify-center items-center ">
        <Card2
          title="HTML"
          description="Projects Done using HTML and foundational web technologies."
          image ={Html}
        />
        <Card2
          title="CSS"
          description="Projects showcasing advanced layouts and responsive designs using CSS."
          image={CSS}
        />
        <Card2
          title="JavaScript"
          description="Interactive and dynamic web projects built using vanilla JavaScript."
          image={JS}
        />
        <Card2
          title="Node.js"
          description="Server-side applications built using Node.js and JavaScript."
         image={Node}
        />
        <Card2
          title="React.js"
          description="Front-end applications created with React, focusing on UI components and state management."
          image={React}
        />
        <Card2
          title="Python"
          description="Scripts and web applications built with Python, including automation and data processing."
          image={Python}
        />
        <Card2
          title="SQL"
          description="Database management and query operations using SQL for efficient data storage."
          image={SQL}
        />
        <Card2
          title="C++"
          description="High-performance applications and system-level programming done with C++."
          image={Cpp}
        />
      </div>
      {/* Top Section End */}

      {/* Bottom Section Start */}
      <div className="flex flex-wrap gap-5 lg:flex-nowrap">
        <div className="basis-full rounded-xl border border-dashed p-5 lg:basis-1/4 bg-gradient-to-r from-slate-300 via-white to-pink-100 text-white">
          <div className="flex flex-col items-center text-center">
            <FaGithub className="text-4xl mb-4" /> {/* GitHub icon */}
            <Card1
              title="GitHub Profile"
              description="An overview of managing repositories and collaborating on code using GitHub."
            />
          </div>
        </div>

        <div className="basis-full rounded-xl border border-dashed p-5 lg:basis-1/4 bg-gradient-to-r from-slate-300 via-white to-pink-100 text-white">
          <div className="flex flex-col items-center text-center">
            <FaLinkedin className="text-4xl mb-4" /> {/* LinkedIn icon */}
            <Card1
              title="LinkedIn Profile"
              description="Tips for building a professional LinkedIn profile to showcase your skills and connect with peers."
            />
          </div>
        </div>

        <div className="basis-full rounded-xl border border-dashed p-5 lg:basis-1/4 bg-gradient-to-r from-slate-300 via-white to-pink-100 text-white">
          <div className="flex flex-col items-center text-center">
            <RxVercelLogo className="text-4xl mb-4" /> {/* Vercel logo */}
            <Card1
              title="Vercel Deployment"
              description="A guide on deploying your projects seamlessly on Vercel for hosting and scaling web applications."
            />
          </div>
        </div>

        <div className="basis-full rounded-xl border border-dashed p-5 lg:basis-1/4 bg-gradient-to-r from-slate-300 via-white to-pink-100 text-white">
          <div className="flex flex-col items-center text-center">
            <FaUserCircle className="text-4xl mb-4" /> {/* User circle icon */}
            <Card1
              title="Personal Web Portfolio"
              description="Learn how to create a personal portfolio to showcase your projects and skills online."
            />
          </div>
        </div>
      </div>
      {/* Bottom Section End */}
    </div>
  );
};

```


# 11. `Projects` Component

## Overview

The `Projects` component is designed to showcase a collection of project cards, each representing a unique project. This component utilizes the `Card3` component to display project titles, descriptions, images, and links to live demos.

## Features

- Responsive design that adapts to various screen sizes.
- Each project card includes:
  - Project title
  - Brief description
  - An image representing the project
  - A link to the live project

## Code Summary

The following is the implementation of the `Projects` component in React:

```jsx
//Projects.jsx
import React from "react"; // Importing React library
import Card3 from "./Card3"; // Importing the Card3 component for displaying individual projects
import Gym from "../images/Gym.png"

// Defining the Projects component
const Projects = () => {
  return (
    <div className="gap-5 mt-5 p-5"> {/* Main container for the projects section */}
      <div className="basis-full rounded-xl border border-dashed p-5 bg-gradient-to-r from-slate-300 via-white to-pink-100 flex flex-wrap gap-9 justify-center items-center">
        {/* Individual project cards */}
        <Card3
          title="Gym Fitness Website" // Title of the project
          description="Website for Fitness" // Description of the project
          image={Gym} // Path to the project image
          projectLink="https://arunkumar069.github.io/GymfitnessWebsite/" // Link to the live project
        />
        <Card3
          title="Gym Fitness Website" // Title of the project
          description="Website for Fitness" // Description of the project
          image={Gym} // Path to the project image
          projectLink="https://arunkumar069.github.io/GymfitnessWebsite/" // Link to the live project
        />
        <Card3
          title="Gym Fitness Website" // Title of the project
          description="Website for Fitness" // Description of the project
          image={Gym} // Path to the project image
          projectLink="https://arunkumar069.github.io/GymfitnessWebsite/" // Link to the live project
        />
      </div>
    </div>
  );
};

export default Projects; // Exporting the Projects component for use in other parts of the application

```

# 12. `ServicesLayout` Component

## Overview

The `ServicesLayout` component displays a grid layout of service offerings, utilizing the `Card4` component for visual representation. Each service card includes an icon, a title, and a description, providing users with an overview of available services.

## Features

- Responsive grid layout that adapts to different screen sizes.
- Each card displays:
  - A relevant icon representing the service
  - Title of the service
  - Brief description of the service offered

## Code Summary

The following is the implementation of the `ServicesLayout` component in React:

```jsx
//ServicesLayout.jsx
import Card4 from "./Card4"; // Importing the Card4 component for individual service cards
import {
  FaCode,
  FaChartLine,
  FaMobileAlt,
  FaSearch,
  FaProjectDiagram,
  FaShoppingCart,
} from "react-icons/fa"; // Importing icons from react-icons

// Defining the ServicesLayout component
const ServicesLayout = () => {
  return (
    <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 p-5"> {/* Grid container for service cards */}
      {/* Individual service cards */}
      <Card4
        title="Websites Using MERN Stack" // Title of the service
        description="Build dynamic, high-performance web applications with a modern tech stack." // Description of the service
        icon={<FaCode />} // Icon representing the service
      />
      <Card4
        title="Creating Dashboards with Power BI" // Title of the service
        description="Transform data into interactive dashboards for insightful decision-making." // Description of the service
        icon={<FaChartLine />} // Icon representing the service
      />
      <Card4
        title="Responsive Web Design" // Title of the service
        description="Deliver mobile-friendly and visually appealing designs for all devices." // Description of the service
        icon={<FaMobileAlt />} // Icon representing the service
      />
      <Card4
        title="SEO Optimization" // Title of the service
        description="Boost your site's visibility with strategic SEO practices." // Description of the service
        icon={<FaSearch />} // Icon representing the service
      />
      <Card4
        title="API Development" // Title of the service
        description="Create robust APIs for seamless data integration and communication." // Description of the service
        icon={<FaProjectDiagram />} // Icon representing the service
      />
      <Card4
        title="E-commerce Solutions" // Title of the service
        description="Build user-centric online stores that enhance customer experience." // Description of the service
        icon={<FaShoppingCart />} // Icon representing the service
      />
    </div>
  );
};

export default ServicesLayout; // Exporting the ServicesLayout component for use in other parts of the application


```

# 13. `AboutLayout` Component

## Overview

The `AboutLayout` component presents a summary of an individual's profile, skills, and availability for freelance work. It utilizes the `Card4` component to display each section in a visually appealing manner, providing information about the person in a structured format.

## Features

- Responsive layout that adapts to both mobile and desktop screens.
- Each card includes:
  - An icon representing the section
  - A title summarizing the section
  - A brief description with relevant information

## Code Summary

The following is the implementation of the `AboutLayout` component in React:

```jsx
//AboutLayout.jsx
import {
  FaCode,
  FaMobileAlt,
  FaSearch,
  FaProjectDiagram,
} from "react-icons/fa"; // Importing icons from react-icons
import Card4 from "./Card4"; // Importing the Card4 component for individual information cards

// Defining the AboutLayout component
export const AboutLayout = () => {
  return (
    <div className="flex flex-col lg:flex-row flex-wrap gap-5 p-5 justify-center items-center">
      {/* Card 1 - About Arun Kumar */}
      <div className="flex-1">
        <Card4
          title="About Me" // Title of the section
          description="I'm Arun Kumar, currently pursuing B.Tech CSE at CT Group of Institutions. Passionate about coding and content creation, I aim to make technology accessible and user-friendly for all." // Description of the individual
          icon={<FaCode />} // Icon representing coding
        />
      </div>

      {/* Card 2 - Frontend Developer */}
      <div className="flex-1">
        <Card4
          title="Frontend Developer" // Title of the section
          description="I specialize in creating seamless digital experiences, combining coding expertise with design creativity to build user-centric solutions." // Description of the frontend development skills
          icon={<FaMobileAlt />} // Icon representing mobile development
        />
      </div>

      {/* Card 3 - Contact Info */}
      <div className="flex-1">
        <Card4
          title="Contact Info" // Title of the section
          description="Phone: 9877275894 | Email: madhavarora132005@gmail.com | City: Hoshiarpur" // Contact information
          icon={<FaSearch />} // Icon representing search/contact
        />
      </div>

      {/* Card 4 - Freelance Availability */}
      <div className="flex-1">
        <Card4
          title="Freelance Availability" // Title of the section
          description="Available for freelance projects. Let’s create something amazing together and make tech magic happen!" // Description of freelance availability
          icon={<FaProjectDiagram />} // Icon representing project work
        />
      </div>
    </div>
  );
};


```

# 14. `ContactForm` Component

## Overview

The `ContactForm` component allows users to reach out with inquiries or questions. It collects the user's name, email, and message, and submits this data through a form. The component uses a modern card layout and includes icons for an enhanced user experience.

## Features

- Responsive design that adapts to different screen sizes.
- Form fields for user input with validation.
- Icons associated with each input field.
- Alternative contact method via email.

## Code Summary

The following is the implementation of the `ContactForm` component in React:

```jsx
//ContactForm.jsx
"use client"; // Indicates this file uses client-side rendering
import { Envelope, PaperPlane, User } from "phosphor-react"; // Importing icons from Phosphor
import {
  Button,
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
  Divider,
  Input,
  InputIcon,
  Label,
} from "keep-react"; // Importing UI components from keep-react

// Defining the ContactForm component
export const ContactForm = () => {
  // Function to handle form submission
  const handleSubmit = (e) => {
    e.preventDefault();
    // Implement form submission logic here (e.g., send data to a backend service)
  };

  return (
    <div className="p-3">
      <Card className="max-w-sm mx-auto my-4">
        <CardContent className="space-y-3">
          <CardHeader>
            <CardTitle>Contact Me</CardTitle> {/* Title of the contact form */}
            <CardDescription>
              Feel free to reach out with any questions or inquiries!
            </CardDescription> {/* Description of the form */}
          </CardHeader>

          <form onSubmit={handleSubmit} className="space-y-4">
            {/* Name Input Field */}
            <fieldset className="space-y-1">
              <Label htmlFor="name">Name*</Label>
              <div className="relative">
                <Input
                  id="name"
                  type="text"
                  placeholder="Enter your name"
                  className="ps-11"
                  required
                />
                <InputIcon>
                  <User size={19} color="#AFBACA" /> {/* User icon */}
                </InputIcon>
              </div>
            </fieldset>

            {/* Email Input Field */}
            <fieldset className="space-y-1">
              <Label htmlFor="email">Email*</Label>
              <div className="relative">
                <Input
                  id="email"
                  type="email"
                  placeholder="Enter your email"
                  className="ps-11"
                  required
                />
                <InputIcon>
                  <Envelope size={19} color="#AFBACA" /> {/* Email icon */}
                </InputIcon>
              </div>
            </fieldset>

            {/* Message Input Field */}
            <fieldset className="space-y-1">
              <Label htmlFor="message">Message*</Label>
              <div className="relative">
                <Input
                  id="message"
                  as="textarea"
                  rows="4"
                  placeholder="Write your message"
                  className="ps-11"
                  required
                />
                <InputIcon>
                  <PaperPlane size={19} color="#AFBACA" /> {/* Paper plane icon */}
                </InputIcon>
              </div>
            </fieldset>

            {/* Submit Button */}
            <Button type="submit" className="!mt-3 block w-full">
              Send Message
            </Button>
          </form>

          <Divider>Alternatively</Divider> {/* Divider for alternative contact method */}
          <div className="text-center">
            <p>
              If you prefer, you can also reach out to me via email at{" "}
              <a
                href="mailto:your-email@example.com" // Replace with your email address
                className="text-blue-600 underline"
              >
                arun00kumar069@gmail.com
              </a>
            </p>
          </div>
        </CardContent>
      </Card>
    </div>
  );
};
 
 ```

 # CSS Stylesheet

This CSS file includes styles for the `Keep React` library and custom styles for components like hexagons and shadow effects.

## Overview

The styles are divided into two main sections:
1. **Global Styles**: These include imports for the `Keep React` CSS framework and Tailwind CSS utilities.
2. **Custom Styles**: Custom styles for specific components, such as box shadows and hexagonal shapes.

## Global Styles

### Imports

```css
@import "keep-react/css";  /* Importing Keep React CSS styles */
@tailwind base;            /* Importing Tailwind CSS base styles */
@tailwind components;      /* Importing Tailwind CSS component styles */
@tailwind utilities;       /* Importing Tailwind CSS utility styles */
```

# `index.css`

```jsx

@import "keep-react/css";
@tailwind base;
@tailwind components;
@tailwind utilities;



.customshadow
{

box-shadow: -13px 12px 15px 8px black;


}

/* HexagonPortfolio.css */
/* HexagonPortfolio.css */
.hexagon {
    width: 100%; /* 100% of the parent */
    height: 100%; /* 100% of the parent */
    position: relative;
    clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
    overflow: hidden;
    transition: border-color 0.3s ease;
}

.hexagon:hover {
    border-color: #6b46c1; /* Change border color on hover */
    animation: pulse 1.5s infinite; /* Add pulse animation */
}

@keyframes pulse {
    0% {
        border-color: #6b46c1; /* Starting color */
        transform: scale(1); /* Starting scale */
    }
    50% {
        border-color: #b794f4; /* Midpoint color */
        transform: scale(1.05); /* Scale up */
    }
    100% {
        border-color: #6b46c1; /* End color */
        transform: scale(1); /* Scale back */
    }
}


```

# App.jsx

The `App.jsx` file serves as the main entry point for the React application. It organizes and renders the primary components that make up the application's user interface.

## Overview

This file imports and incorporates several key components, providing a structured layout for the application. The components are organized in a logical flow, starting from the navigation bar and culminating in the contact form.

## Components

1. **Navbar1**: 
   - Renders the navigation bar for easy access to different sections of the website.

2. **Home**: 
   - Displays the landing section or introductory content for the application.

3. **Heading**: 
   - A reusable component that displays section titles. It is used multiple times throughout the application for consistency in headings.

4. **Skills**: 
   - Renders a section highlighting the skills possessed by the individual or organization.

5. **Projects**: 
   - Displays a collection of projects undertaken, showcasing work and accomplishments.

6. **ServicesLayout**: 
   - Highlights the services offered, providing users with information on what they can expect.

7. **AboutLayout**: 
   - Contains details about the individual or organization, providing context and background information.

8. **ContactForm**: 
   - A form that allows users to reach out with inquiries, providing fields for name, email, and message.

## Code Structure

Here’s a breakdown of the `App.js` code:

```jsx
//App.jsx
import Home from "./components/Home"; // Import Home component
import { Skills } from "./components/SkillsSection"; // Import Skills section
import { Navbar1 } from "./components/Navbar1"; // Import Navbar
import Projects from "./components/Projects"; // Import Projects section
import Heading from "./components/Heading"; // Import Heading component
import ServicesLayout from "./components/ServicesLayout"; // Import Services section
import { ContactForm } from "./components/ContactForm"; // Import Contact Form
import { AboutLayout } from "./components/AboutLayout"; // Import About section

function App() {
  return (
    <div className="bg-[#527385]"> {/* Main container with background color */}
      <Navbar1 /> {/* Navigation Bar */}
      <Home /> {/* Home Section */}
      <Heading title="My Skills" /> {/* Skills Section Heading */}
      <Skills /> {/* Skills Section */}
      <Heading title="My Projects" /> {/* Projects Section Heading */}
      <Projects /> {/* Projects Section */}
      <Heading title="Services I provide" /> {/* Services Section Heading */}
      <ServicesLayout /> {/* Services Section */}
      <Heading title="About" /> {/* About Section Heading */}
      <AboutLayout /> {/* About Section */}
      <Heading title="Contact Me" /> {/* Contact Section Heading */}
      <ContactForm /> {/* Contact Form */}
    </div>
  );
}

export default App; // Export the App component

```

  
