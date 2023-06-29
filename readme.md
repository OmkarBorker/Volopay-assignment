# VoloPay Assignment

## Live

Open [https://volopaydashboard.netlify.app](https://volopaydashboard.netlify.app) to view it in your browser.

## Local Development Setup

Clone this repo by running
`git clone https://github.com/OmkarBorker/Volopay-assignment.git`.

In the project directory, you can run:

1. Install dependencies

```bash
yarn install
```

2. Update **BASE_URL** in src/components/App.jsx file

```diff
- const BASE_URL = "https://obvious-healthy-larkspur.glitch.me" ;

+ const BASE_URL = "http://localhost:3500";
```

3. Start the server

```bash
yarn start
```

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

### Running JSON-SERVER locally

In a separate terminal tab, inside the project directory run:

```bash
yarn run db-server
```

Runs the JSON Server locally.
Open [http://localhost:3500](http://localhost:3500) to view it in your browser.

he app starts by importing the necessary dependencies and components such as React, useState, useEffect, axios, Header, SubHeader, and Cards.

The BASE_URL constant is set to the API endpoint where the card data is fetched from. It's currently set to "https://api.jsonserve.com/50vgAn/". Adjust this URL according to your API endpoint.

The YOUR_OWNER_ID constant is set to the specific owner ID for which the "your" tab should filter the cards. Modify this ID based on your requirements.

The App component is defined as a functional component.

Inside the App component, state variables are declared using the useState hook. These variables include cards, filter, searchTerm, and page.

The handleTabClick function is defined to handle the tab clicks in the subheader. Depending on the clicked tab, it filters the cards accordingly. If the "your" tab is clicked, it filters the cards based on the YOUR_OWNER_ID. If the "blocked" tab is clicked, it filters the cards with the status property set to "blocked". Otherwise, it clears the existing cards and fetches new cards.

The fetchCards function is responsible for making API requests to fetch the cards data. It constructs the appropriate URL based on the filter and searchTerm values and performs a GET request using axios. The retrieved data is then appended to the existing cards using the setCards function. The page variable is also incremented to keep track of the pagination.

The handleScroll function is triggered when the user scrolls the window. It checks if the user has reached the bottom of the page and calls the fetchCards function to load more cards.

The useEffect hook is used to fetch the initial cards data when the component mounts. It also adds an event listener for the scroll event to trigger the handleScroll function.

Finally, the App component renders the main structure of the app. It includes the Header, SubHeader, and Cards components. The necessary props are passed to the SubHeader and Cards components to handle interaction and data display.

That's an overview of the functioning of the React app. It fetches cards data from the API, allows filtering based on tabs, supports pagination, and displays the cards using the Header, SubHeader, and Cards components.
