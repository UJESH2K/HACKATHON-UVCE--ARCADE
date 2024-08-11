Arcade-DM
Arcade-DM is a web application that utilizes Machine Learning to predict floods based on weather data and various historical records.

Getting Started
Clone the project and install dependencies
Activate virtual environment
Run pip install -r requirements.txt
Execute python app.py
You're Done!
Inspiration
Floods are among the most dangerous and frequent natural disasters globally. According to the World Resources Institute, over 80% of India's population—1.08 billion people—are at risk due to floods. Floods cause an economic loss of nearly 40 billion USD annually worldwide, with 15 billion USD in India alone. In the recent Kerala flood tragedy, over 100 lives were lost, and more than 15,000 homes and buildings were destroyed. Such floods occur almost every year in flood-prone areas, causing significant damage. The primary cause is the overflow of rivers, reservoirs, and other water bodies due to heavy monsoon rains.

Climate change is exacerbating the risk of floods worldwide, particularly in coastal and low-lying areas, due to its impact on extreme weather events and rising sea levels. The increase in global temperatures contributes to more intense hurricanes and heavier rainfall, while melting glaciers contribute to rising sea levels, creating chronic flooding risks. As a result, the frequency and impact of floods are increasing.

Our team sought to address this issue by creating Arcade-DM, a web application designed to predict floods and their impacts before they occur. The application presents this information through an interactive graphical format, making it engaging and easy for individuals and governments to understand.

What It Does
Arcade-DM provides a solution for flood prediction in India. It uses advanced machine learning algorithms to forecast future floods based on weather data—such as precipitation, wind speed, humidity, temperature, and cloud cover—while allowing users to visualize current and upcoming flood risks. The app features four core components:

1. Plots
The plots page includes three visualizations: bubble plots that display flood predictions, damage forecasts, and heavy rainfall data across India. Key plots include:

The flood prediction plot, indicating potential flood locations with red dots.
The precipitation plot, showing current precipitation levels nationwide, with larger bubbles for higher precipitation.
The damage analysis plot, illustrating estimated monetary damage based on flood risk predictions and population size, with bubble sizes reflecting damage extent in USD.
2. Heatmaps
The heatmaps provide visual representations of flood predictions, damage forecasts, and heavy rainfall across India. Key heatmaps include:

The damage analysis heatmap, displaying predicted monetary damage with a colorscale indicating severity in USD.
The precipitation heatmap, showing current precipitation levels, with darker red areas representing higher volumes.
The flood prediction heatmap, illustrating the likelihood of floods based on current environmental factors, marked by darker red spots.
3. Satellite Images
Our satellite image analysis shows precipitation volumes over various Indian cities for different months. We used netCDF4 formatted data from NASA's Global Precipitation Measurement Project, processed it with libraries like numpy, matplotlib, and cartopy, and displayed the images on our web application.

4. Predict Page
On the predict page, users enter any city name, and the app fetches real-time weather forecast data for that city. The machine learning model then generates instantaneous results, including flood predictions, temperature, maximum temperature, humidity, cloud cover, wind speed, and precipitation.

How We Built It
The Dataset
To predict floods using machine learning, we scraped data from http://floodlist.com/tag/india with Python's Beautiful Soup 4 library. We gathered information about past and current floods in India, including their dates and locations. The Visual Crossing weather API provided historical weather data, which we augmented to increase dataset diversity for training our model.

ML Model
Our machine learning model, developed using the Python scikit-learn library, involved generating a dataframe with pandas and experimenting with various models. The Random Forest Classifier achieved the highest accuracy of 98.71% on the test set, and we saved this model in a pickle file.

Data Visualization
We obtained data for major Indian cities (about 200) with latitude, longitude, and population, and integrated weather factors using the weather API. We plotted this data using Plotly Chart Studio, creating scatter plots, heatmaps, and bubble plots to represent flood predictions, precipitation analysis, and damage estimates. Geo-referenced satellite images were produced using data from NASA's Global Precipitation Measurement Project.

Front-End and Hosting
The web app is built on the Flask Python framework, with HTML templates styled using CSS and enhanced with JavaScript. 

Challenges We Ran Into
Our main challenge was gathering quality data for building models and visualizations. Limited existing data required us to use web scraping and APIs to compile an accurate dataset. Integrating Plotly visualizations with our web app was challenging, and we encountered git merge conflicts due to varying encodings of CSV files and pickle versions.

What We Learned
We gained extensive experience in web scraping and data mining, learned data manipulation techniques to create effective datasets, and acquired skills in using Plotly for data visualization. Our machine learning expertise grew through model experimentation, particularly with the Random Forest Classifier.

