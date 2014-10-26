---
title       : BMI Calculator
subtitle    : 
author      : David H. Millis
job         : October 26, 2014
framework   : io2012       # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---
## Your BMI (Body Mass Index)

BMI (body mass index) is a measure of body fat based on height and weight. BMI Calculator calculates your body mass index using the following formula:

<b>$$BMI = \frac{(\mbox{weight in kg})}{(\mbox{height in meters})^2}$$</b>

An ideal BMI is in the range from 19.0 to 25.0. A BMI lower than 19.0 indicates that the individual is underweight. A BMI between  25.0 and 30.0 indicates that the individual is overweight. A BMI above 30.0 indicates obesity.

---
## Sample BMI Calculation

Let's consider Steve, whose height is 5'10" and weight is 160 pounds. BMI Calculator does the following calculations:


```r
num_feet <- 5; num_inches <- 10; num_weight_lb <- 160

num_height_inches <- num_feet * 12 + num_inches
num_height_meters <- num_height_inches * 0.025
num_weight_kg <- num_weight_lb * 0.45
num_bmi <- num_weight_kg/num_height_meters^2

print (num_bmi)
```

```
## [1] 23.51
```

---
## BMI Categories

BMI Calculator now determines Steve's body fat category:


```r
num_bmi <- 23.51; str_bmi <- format(num_bmi, digits=2)  
if (num_bmi < 19.0) 
  { msg <- "Underweight"
} else if (num_bmi >= 19.0 && num_bmi < 25.0) 
  { msg <- "Ideal BMI"
} else if (num_bmi >= 25.0 && num_bmi < 30.0) 
  { msg <- "Overweight"
} else if (num_bmi >= 30.0 && num_bmi < 34.5) 
  { msg <- "Obese" }
paste(str_bmi, " ", msg)
```

```
## [1] "24   Ideal BMI"
```
So Steve has a normal BMI for his height.

---
## Using BMI Calculator

To use BMI Calculator, enter the following information:

- Enter your height, in feet and inches, using the two drop-down boxes.
- Enter your weight, in pounds, using the slider.

BMI Calculator will manage the unit conversions, and will calculate your BMI.

## Features of BMI Calculator

- Simple graphical interface.
- Conversion of height and weight to metric values is done automatically.
- Slider input for weight makes it easy to test different weight scenarios. You can quickly find a target weight that would move you from an undesirable BMI to a healthier BMI, just by moving the slider.
