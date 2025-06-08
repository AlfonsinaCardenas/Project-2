# Project 2 - UI/UX Design with Streamlit Report 

**Name:** Alfonsina Cardenas

**Course:** Human-Computer Interaction

**Project Theme:** The Weather

**Date:** June 6, 2025

In this project, I developed a web app using Streamlit and API requests. My web application is about the weather, and it allows the user to explore different metrics of the current weather, such as temperature, humidity, and pressure.  It also provides them with the forecast (which goes up to about a day), a map with coordinates, both measures of temperature, and graphs for visualization. 

# 🎯 Usability Goals

**Effectiveness**

One of my primary goals was effectiveness, ensuring users could easily navigate the web application and access the weather details they care about, such as humidity, temperature, and wind speed. The data is retrieved from a reliable API (OpenWeatherMap), which ensures the information is accurate and trustworthy.

**Efficiency**

Another key goal was efficiency, or how quickly and easily users can perform tasks. In the application, once users select a location and click "Get Weather," the weather data loads instantly, ready to explore and analyze with minimal waiting time.

**Learnability**

Learnability refers to how easy it is for new users to understand and begin using the app. To support this, I included clear instructions, labeled input fields, and friendly feedback messages. For example, success boxes confirm when weather data has loaded successfully, and information messages at the end of each page help guide users to the next step (choosing an option from the sidebar).

**Memorability**

When users return to the design after a period of time, they should find it easy to remember how to navigate the app. The design of the app is consistent and repeatable. The text box and select box process is simple, so they can immediately begin using the app and getting the weather. Also, the instructions at the top of each feature helps the user understand what to do.

**Error Prevention**

When the user inputs a location that is not identified by the API, they will get an error message to let them know. The message will also tell them to check their input again and retry.

**User Satisfaction**

User satisfaction describes how pleasant it is to use the design of the app. The users will be able to interact with the app, such as changing the background color and moving sliders to find out how certain metrics will affect the weather and themselves. In addition, feedback and messages will be given in a friendly tone that makes the user more comfortable.

# 🧠 Design Process

## Weather Details Page

For the weather details page, I wanted to include the current weather information for a specific location chosen by the user.  When I tried the API with the text box, it would only let me write the city and the country, which would make it difficult for the user to find the specific location they were looking for since many cities around the country have the same name.  To fix this, I integrated the geocoding endpoint which allowed the user to write the name of the city, state, and country for a more specific search. Then, the select box let's us explore all the different states and even countries that have cities with the same name. For example, when we write "Rome" in the text box, the select box shows us options like "Rome, Lazio, IT" or "Rome, Georgia, US". The geocoding endpoint also provides the coordinates, which helped me create the map and the checkbox with said coordinates. 

I decided to also add the color_picker widget because I did not like how it looked with a basic white background. Instead of making the decision myself of what color the web app should be, I gave the users the option to choose based on their own preference, making the app more flexible and interactive.

For weather, I did not want to show only the temperature, so I looked at other weather apps to see what other information I could provide.  I chose to add metrics such as humidity, pressure, wind speed, and the current weather, such as cloudy, clear, and rainy.

Lastly, since people have their own preferences for temperature scales, I added an interactive table that provided the temperature, feels life, minimum, and maximum in both Celsius and Fahrenheit.

## Forecast Page

While I was thinking of what information to include for the chart requirement, I got the idea of creating a forecast section that would show different metrics and how they would change over time. I also looked at other weather apps for this and finally decided to include 5 metrics: temperature, humidity, wind speed, precipitation, and pressure. I used a select box for the graph layout because I did not want the page to feel too cluttered. I figured if the page was too crowded, it would end up confusing and frustrating the user. 

For the expanders, I was thinking about how to provide more information about the metrics in a way that would look more aesthetically pleasant. I think it was a good option because it keeps the page clean, and gives the user more flexibility because they can choose whether or not to receive the information.  The "Fun Fact" section was added because I became curious about certain things about the metrics, like how fast the wind needs to be for it to be considered a hurricane, so I figured users would also like to read some fun facts.

Lastly, since people are used to different weather depending on where they live, I decided to add sliders that show how each metric (like temperature, humidity, or wind) can affect how the weather feels. For example, I was born in a place with a dry climate, so when I moved to Miami, the humidity was a big change. This feature helps users feel more involved, and it also teaches them how these weather conditions can impact comfort and daily life.


# 🌐 API Integration

## WeatherOpenMap API

I used 

# Interactive Widgets

# 📝 Application of HCI Design Principles

**Visibility**

Important features are clearly shown in big letters, such as titles and subheaders. Widgets like text and select boxes are big enough for the user to immediately see and interact with, and messages are placed on top for better understanding. Every section is clearly labeled, such as the map, current weather, temperature details, and forecast. The app also has a map, table, and line charts for visualization, as well as interactive sliders with info/success/warning/error boxes. The type of box chosen depends on the number the user picks from the slide, which adds to the visualization. In addition, emojis are used throughout the web app to help the user see where there is text, and to ensure a more friendly tone.

**Feedback**

The web application uses success and error boxes to inform the user when the data has been successfully loaded, or when the API does not recognize a certain location. Also, an information box was added to show the current date and time, which updates every time the user interacts with the app. This means the data is refreshing constantly and ensures the user is receiving information in real time. The info/success/warning/error boxes were also used to give the user friendly information about the different metrics of the weather, such as what to wear depending on the temperature, and what to expect depending on the humidity percentage.

**Consistency**

The web application looks similar accross all pages. The same layout is used, same fonts, and emojis and other icons are used all throughout.  This prevents confusion and ensures the user remains engaged. In the forecast page, the only thing that changes is the information depending on the metric the user chooses, but the overall layout stays the same with features like: line charts, expander for information, fun fact, and  slider.

**Flexibility**

The web app allows the user to move freely.  They can interact with the app with actions such as: changing the background color, searching for different cities at any time, deciding whether or not they would like to see the coordinates, opening the expander for more information, and moving the sliders. In addition, the select box in the beginning gives the user an opportunity to explore the different cities around the world (and even country) that have the same name.

# Conclusion








