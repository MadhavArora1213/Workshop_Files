# Portfolio Website

This is a simple yet elegant portfolio website built with React,Keep React(UI Library) and Tailwind CSS. The project includes responsive components such as a portfolio image display and dynamic text writer and other features also.

## Features

- Responsive layout for different screen sizes.
- A portfolio image component that scales with the screen size.
- Modern and sleek UI using Tailwind CSS.
- Easily customizable components.

## Components

### 1. `Navbar` Component

The Navbar component is an essential part of the portfolio website, providing seamless navigation and a professional, user-friendly experience. It integrates a responsive design using the Keep React UI Library and Tailwind CSS, ensuring smooth adaptability across different screen sizes.

The code showcases how to build a responsive navbar with dropdown functionality. The Navbar1 component consists of the following key elements:

NavbarBrand: Displays the logo of the website.
NavbarList: Contains the primary navigation items with a clean and modern design.
Dropdown Avatar: Displays the user's profile picture in the form of an avatar with an accessible dropdown menu that lists the same navigation items for ease of use.
NavbarCollapse: Handles the collapse of the navigation menu for smaller screens, ensuring an optimal user experience on mobile devices.

```jsx
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

export const Navbar1 = ({
  profile = "/src/images/Profile.jpeg",
  logo = "/src/images/Html.png",
}) => {
  return (
    <Navbar className="px-5 bg-gradient-to-t from-black to-gray-600">
      <NavbarContainer>
        <NavbarBrand>
          <img src={logo} alt="keep" className="w-[50px] h-[50px]" />
        </NavbarBrand>
        <NavbarList>
          <NavbarItem className=" text-white font-semibold">Home</NavbarItem>
          <NavbarItem className=" text-white font-semibold">Skills</NavbarItem>
          <NavbarItem className=" text-white font-semibold">
            Projects
          </NavbarItem>
          <NavbarItem className=" text-white font-semibold">
            Services
          </NavbarItem>
          <NavbarItem className=" text-white font-semibold">About</NavbarItem>
          <NavbarItem className=" text-white font-semibold">Contact</NavbarItem>
        </NavbarList>
        <NavbarList>
          <Dropdown placement="bottom-end">
            <DropdownAction asChild>
              <Avatar>
                <AvatarImage src={profile} />
              </Avatar>
            </DropdownAction>
            <DropdownContent className="border border-metal-100">
              <DropdownList>
                <DropdownItem className=" text-white font-semibold">
                  Home
                </DropdownItem>
                <DropdownItem className=" text-white font-semibold">
                  Skills
                </DropdownItem>
                <DropdownItem className=" text-white font-semibold">
                  Projects
                </DropdownItem>
                <DropdownItem className=" text-white font-semibold">
                  Services
                </DropdownItem>
                <DropdownItem className=" text-white font-semibold">
                  About
                </DropdownItem>
                <DropdownItem className=" text-white font-semibold">
                  Contact
                </DropdownItem>
              </DropdownList>
            </DropdownContent>
          </Dropdown>
        </NavbarList>
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

