<p align="center">
  <img src="images/logo.png" width="750" />
</p>

We are a team of 4 students who participated in the [2025 NASA Space Apps Challenge](https://www.spaceappschallenge.org/2025/):

- [Shun Nagata](https://github.com/shunnagata35)
- [Hanna Suzuki](https://github.com/HSSBoston/)
- Rei Nagata
- Konomi Karube

NASA Space Apps Challenge is an annual hackathon event (or an innovation incubation and civic engagement program) where NASA puts out about 20 challenges for participants around the world to develop innovative solutions.

We participated in the [Boston regional contest](https://www.spaceappschallenge.org/2025/local-events/boston/) of Space Apps, and won Honorable Mention and Amazon AWS Award. 

- [Official team web page](https://www.spaceappschallenge.org/2025/find-a-team/futurescape-navigators/?tab=project) at SpaceAppsChallenge.org
- [7-page project summary](https://docs.google.com/presentation/d/1e3Kvd_qfm2isCm5xuYmzgIN8jB0gbaObtXhRDeRNjJ0/edit?slide=id.g1b0e7df1845_2_75#slide=id.g1b0e7df1845_2_75)
- [Oral Presentation slides](https://docs.google.com/presentation/d/166a0fMkDra3B9j8fxCaG4QLcnFUE1G8V7Rina4QTMiw/edit?usp=sharing) at Boston local judging


## Project Summary:

The FutureSpace Navigators is a team of four high school students. We worked on a wide range of data analytics to estimate the likelihood of certain weather conditions at a location and time with NASA EarthData.

#### (1) Estimating heat stress and risk in outdoor activities

We estimated heat stress in outdoor activities. It is not surprising to experience extremely high temperature and heat stress in urban cities. It is a critical threat for both the tourists and the residents of those cities. 

Wet Bulb Globe Temp indicates the heat stress on the body in direct sunlight by measuring various factors. WBGT is recommended by major federal, state and professional agencies. Some of them have announced WBGT-based heat policies. It suggests how much and how often you need to rest and get hydrated according to the current WBGT. 

Using daily maximum WBGT data from NASA, we generated histograms and boxplots with different history ranges. We found that 5-year historical data give me the best estimate. With 5-year data, we also compared multiple cities in terms of WBGT outlook. We created violin plots, which are basically a combination of histograms and boxplots. They show that the WBGT distribution in New York City looks like a normal distribution, and Tokyo’s has a very high mean and median with a long-tail. Tokyo's median is higher than those in Taipei and Tunis. We also generated cumulative distributions, which shows the probability of risky conditions.

#### (2) Estimating the pleasure and productivity of fishing

We estimated the pleasure and productivity of fishing. In order to estimate the pleasure part, we considered 3 factors: daily max air temperature, daily minimum-maximum temperature difference, and daily total precipitation. For the productivity part, we considered daily water temperature average, max/min, daily wind speed average, and daily rise above mean sea level. 

Then, we normalized each pleasure factor between 0 and 1. For example, the maximum air temperature is normalized with a few equations. Basically, the normalized temperature is closer to 1 as the temperature goes closer to the optimal (the most comfortable) temperature. It is closer to 0 as the temperature goes farther away from the optimal temperature. 

We also quantified the expected fishing result based on the productivity factors. We call it the productive fishing spot index, aka PFSI. It is a numerical number between 0 and 1, which is calculated with another equation. Simply put, PFSI goes closer to 1 as a fishing spot's environmental conditions are closer to the optimal. 

We calculated pleasure factors and PFSI for each of the well-known fishing locations and drew a radar chart to display the data and information. In the radar chart, each polygon represents a spot, and a larger polygon means a more favorable spot in the pleasure and productivity of fishing.

#### (3) Estimating the chances of weather-related pain and other symptoms

One of our team members, Konomi, often notices that, when the weather is bad, she tends to have headaches. She has also observed that she has headaches frequently in fall and winter, especially when the weather is rainy. 

Research studies show that changes in barometric pressure can cause headaches, fatigue, or join pain, a condition known as meteoropathy. Around 30% of the world population, or about 2.4 billion people, experience similar symptoms. Although not life-threatening, it can greatly affect quality of life. 

Therefore, we decided to analyze the Barometric Pressure using NASA Earthdata. We visualized the data by making line graphs and histogram. Konomi had a headache at the end of September, so we decided to examine the September barometric pressure data. From this database we noticed significant decline from September 26 to 27. About 9hPa decrease from day before. Research studies have reported that 5hPa decline is the likelihood of someone getting symptoms, so Konomi's headache corresponds to barometric pressure. 

The first four histograms show the frequency of daily barometric pressure over 25 years for each season in Seattle. The second row of histogram shows the 1-day pressure difference during the same. The third row shows cumulative distribution function comparing Seattle, Boston and Miami for each season. In Seattle, summer has only a 4% chance of pressure dropping by 5 hPa, but winter rises to 22%, making symptoms more likely. Boston is slightly higher, while Miami stays below 5%, meaning people there are less likely to get weather related symptoms. 

As a result, we tend to have headaches in fall and winter. This cumulative frequency graph clearly visualizes the dramatic change of barometric pressure after the end of summer to the start of fall. This seasonal changes in pressure may be the reason why Konomi experienced headache at the end of September.

#### (4) Estimating the visibility of auroras

We are also interested in space weather, not just Earth weather! It is about the conditions of solar wind, which is the flow of charged particles from the Sun. They’re usually blocked out by the geomagnetic field, but sometimes they get into Earth’s atmosphere, causing geomagnetic disturbance and auroras. Auroras are actually those particles from the Sun.


Geomagnetic disturbance is continuously measured by many agencies, and a well-known metric is Ap-index. Higher Ap means higher disturbance, meaning higher chance of aurora visibility.

Using this information, we estimated the future aurora visibility at a particular location and time. This can help anyone know when and where to go see them. We also used nighttime cloud cover data and the Bortle scale, which quantifies the sky’s darkness at night.For this, I used Ap data in 9 solar cycles in the past 90 years, and extracted a typical Ap change in a solar cycle as a median curve after data smoothing and other processing.

We also made a visibility table that maps a latitude and Ap value to a visibility chance. The median curve and visibility table allow us to generate the visibility rating for a location’s latitude and a future date. The rating scheme spans from Triple-A to C, inspired by financial credit rating. For example, if you want to go see an aurora in December 2027, Lapland, Finland, has a Triple-A rating, compared to the double B in Oslo and C in Boston.

