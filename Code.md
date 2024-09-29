# Portfolio Website

This is a simple yet elegant portfolio website built with React,Keep React(UI Library) and Tailwind CSS. The project includes responsive components such as a portfolio image display and dynamic text writer and other features also.

## Features

- Responsive layout for different screen sizes.
- A portfolio image component that scales with the screen size.
- Modern and sleek UI using Tailwind CSS.
- Easily customizable components.

## Components

### 1. `PortfolioImage` Component

This component is responsible for displaying the portfolio image with a fully responsive design.

```jsx
import React from "react";

const PortfolioImage = ({ image = "/src/images/portfolio.webp" }) => {
  return (
    <div className="rounded-full flex justify-center items-center max-w-full">
      <img
        className="rounded-full w-48 h-48 sm:w-60 sm:h-60 lg:w-72 lg:h-72 xl:w-80 xl:h-80 object-cover"
        src={image}
        alt="Portfolio"
      />
    </div>
  );
};

export default PortfolioImage;
