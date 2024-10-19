# Meme-Generator Using JAVASCRIPT

# Project Overview
This simple Meme Generator allows users to display wholesome memes on demand. The meme title, image, and author are fetched from an external API and displayed dynamically on the webpage. The design is clean and minimalistic, focusing on ease of use and a pleasant user experience.

# Features
Fetches a random meme from the Wholesome Memes subreddit using the Meme API.
Displays the meme title, image, and author on the page.
A "Generate Meme" button to fetch and display a new random meme.
Responsive design to ensure compatibility across devices.
# Installation
To get a local copy of this project up and running, follow these steps:

# Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/meme-generator.git
Navigate into the project directory:

bash
Copy code
cd meme-generator
Open the index.html file in your web browser to view the app.

# Usage
Once the project is set up:

Open the app in your browser.
Click the "Generate Meme" button to fetch and display a new meme.
The meme's title and author will also be shown along with the image.

# API Used
This project uses the Meme API to fetch data. The endpoint used in this app is:

bash
Copy code
https://meme-api.com/gimme/wholesomememes
This API returns a random meme from the wholesome meme subreddit with the following fields:

title: The title of the post
url: The direct URL to the meme image
author: The Reddit username of the person who posted the meme

# Code Explanation
JavaScript (script.js)
The JavaScript file handles the logic for fetching and displaying memes. It selects the necessary DOM elements and adds an event listener to the "Generate Meme" button. When clicked, it triggers an API call to fetch a new meme and updates the DOM with the meme data.

# Key points from the code:

getMeme function: This function sends a request to the Meme API and processes the returned JSON data. It extracts the meme's title, url, and author and updates the corresponding HTML elements on the page.
Event listener: When the "Generate Meme" button is clicked, it calls the getMeme function to display a new meme.
Here’s a snippet of the JavaScript:

- javascript
Copy code
function getMeme() {
  fetch('https://meme-api.com/gimme/wholesomememes')
    .then((res) => res.json())
    .then((data) => {
      const { author, title, url } = data;
      memeTitle.innerText = title;
      memeImage.src = url;
      authorOutput.innerText = `Meme by: ${author}`;
    });
}
(script)

- CSS (style.css)
The CSS file contains styles to ensure the app looks clean and responsive. Key styles include:

Body styling: Uses a centered layout with Nunito font for a modern look.
Meme container: The container that holds the meme is styled with rounded corners, padding, and a box-shadow for a card-like appearance.
Button styling: The button is designed with a green background and hover effects to enhance user interaction.
Here’s a snippet of the CSS:

- css
Copy code
button {
    border: none;
    padding: 12px 16px;
    background-color: #069179;
    color: white;
    width: 100%;
    border-radius: 8px;
    cursor: pointer;
}
(style)

# Future Improvements
In the future, the app could be enhanced with the following features:

Save memes: Allow users to save their favorite memes to local storage.
Share memes: Provide functionality to share memes directly to social media platforms.
Loading indicator: Add a loading spinner while the meme is being fetched from the API.
Custom meme categories: Allow users to select different meme categories or subreddits.

# Contributing
If you'd like to contribute to the project, follow these steps:

# Fork the repository.
Create a new branch for your feature or bugfix.
Commit your changes and open a pull request with a detailed description.
