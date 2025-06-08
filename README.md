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

I used the **OpenWeatherMap API** to retrieve data in real time. This API has multiple endpoints, and I picked three of them for different uses:

- **Geocoding** (`/geo/1.0/direct`) – Converts city names into geographic coordinates.  
  This endpoint made it possible to use inputs like "City, State, Country" instead of just "City, Country." 
  This enhances user satisfaction by helping them choose between cities with the same name.

- **Current Weather Data** (`/data/2.5/weather`) – Retrieves the current weather for a given location.  
  This is used on the **Weather Details** page to show real-time temperature, humidity, pressure, and more.

- **Forecast** (`/data/2.5/forecast`) – Provides short-term weather forecasts in 3-hour intervals.  
  This is used on the **Forecast** page to generate charts and explore upcoming weather metrics.


# 🧩 Interactive Widgets and Streamlit Features

- **Interactive Table (st.dataframe):** Used to show the current temperature, feels like, minimum, and maximum in both Celsius and Fahrenheit.
  
- **Line Chart (st.altair_chart):** Used to show the forecasts for temperature, humidity, wind speed, precipitation, and pressure.
  
- **Map (st.map):** Used to mark the user’s selected location on the map.
  
- **Button (st.button):** Used to trigger the API call and load weather data after the user confirms their selection.
  
- **Checkbox (st.checkbox):** Used to show the coordinates of the location selected by the user. 
  
- **Feedback Message Boxes:**
  
  _success.st:_ Used to confirm when the data was loaded. Also for some of the feedback of the slider in forecast page.
  
  _st.info:_ Used to show the date and time at the end of each page. Also used in the slider in forecast page.

  _st.warning:_ Used in the sliders for forecast page. For example, when the weather selected was warm.

  _st.error:_ Used to inform the user when the location written is not identified by the API. Also used for the forecast sliders (Hot weather, Strong winds).

- **Selectbox (st.selectbox):** Used to display a list of matching locations, which helps the user select the correct location if there is more than one city with the same name, such as Rome and Miami.

- **Slider (st.slider):** Used to help users explore how different weather metrics (e.g., temperature, humidity, wind speed) affect real-world conditions.

- **Text Input (st.text_input):** Used at the start of the process to allow users to enter a location in the format "City, State, Country"

- **Color (st.sidebar.color_picker):** Used to allow users to change the background color of the web app. It is located in the sidebar.

- **Radio button (st.sidebar.radio):** Used to switch between the Weather Details and Forecast pages. They are located in the sidebar.

- **Sidebar (st.sidebar.radio and st.sidebar.color_picker):** Used to provide the user with an easy way to switch between pages (Weather Details and Forecast), and also to pick a background color for the app.

- **Expander (st.expander):**  Used to hide the explanations about each forecast metric (e.g., temperature, humidity, etc.)  until the user chooses to view them.  
This keeps the page clean and avoids overwhelming users with too much information at once.  
 

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

This project allowed me to apply what I’ve learned about UI/UX design and build a functional, user-centered weather web app. My main goal was to make sure users could explore weather data in a way that felt smooth, clear, and engaging.

By combining API integration with interactive widgets like sliders, expanders, and color customization, I created a layout that’s both informative and easy to navigate. Every design decision, from the use of a select box to prevent crowding, to the inclusion of multiple metrics and personalized feedback, was made with the user experience in mind.

In the future, I would like to explore more features of streamlit, such as adding images. I tried adding a background image of a sky with clouds to make it seem more like a weather app, but I was not able to succeed. Therefore, I would like to work more on features like that and learn as much as I can. In addition, if I develop another weather app, I would include longer forecasts.






