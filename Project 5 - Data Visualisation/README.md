# Analysis of Lyft Bay Wheels Data

**by Gabriel**

## About Bay Wheels

Bay Wheels is a regional public bicycle sharing system in California's San Francisco Bay Area. It was established as Bay Area Bike Share in August 2013. In June 2017 the system was officially re-launched as Ford GoBike in a partnership with Ford Motor Company. After Motivate's acquisition by Lyft, the system was renamed to Bay Wheels in June 2019.

## The Dataset

In this project I analysed Bay Wheels data for January 2020 downloaded from https://www.lyft.com/bikes/bay-wheels/system-data

## Findings of the Exploratory Analysis

Before exploring the dataset, I first assessed and cleaned it. This involved creating categories that separated the data into weekdays and weekends, into the specific days of the week, and converted the duration time of each ride into minutes and hours.

The first step of the exploratory analysis was then to produce univariate analyses. Here I found out that:
- The distribution of ride durations is skewed to the right (with mos trips lasting around 400 seconds) with a long tail (so most rides are short ones but there are some very long rides)
- Bike tended to increase the closer it got to the end of the month
- During weekdays: We can see here a bimodal distribution with peaks at 8h and 17h since that is the time people usually go to and leave work.
- During weekends: we don't see this bimodal distribution since people are not working so we can see more of a normal distribution with the peak being after lunch
- There are more Subscribers than Customers (user_type); app users than clipper users (rental_access_method), weekday rides than weekend rides and the vast majority of bikes are delivered at a different station than they were picked up.

The bivariate and multivariate analyses then followed producing the following findings:
- The numbers of bike rides tends to fall during weekends (with some exceptions)
- Bike rides tend to be longer during weekends
- Customers tend to ride longer than Subscribers during the weekend

## Visual Presentation of Findings

The explanatory analysis focused on using graphic visualisations to find out (1) when the bike rides are used the most and (2) getting insights about who could the biggest users of the platform be and why they used the platform.

The main insights were:
- Bike rides tend to happen more during weekdays and tend to be shorter than during weekends.
- During weekdays, they are strongly concentrated at times in which people are commuting to and from work, suggesting that commuters are an important segment of the market.
- These commuters seem to be more represented by the 'Subscriber' type of user, who also ride the bikes more often at weekdays and for shorter periods. They also have the biggest share of overal rides in the platform.

## Resources

Dataset: https://www.lyft.com/bikes/bay-wheels/system-data.

A number of https://stackoverflow.com/ posts were used to help with the coding.
