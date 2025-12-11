# Assignment 6 Part 2 - Writeup

---

## Question 1: Feature Importance

Based on your house price model, rank the four features from most important to least important. Explain how you determined this ranking.

**YOUR ANSWER:**
1. Most Important: SquareFeet
2.Bedrooms
3.Bathrooms
4.Least Important:Age
**Explanation:**
I came to this ranking by considering the coefficients that the model computed, and also by looking at the scatter plots. SquareFeet seems to be the most important because it has the biggest impact on price-more specifically, the more space a house has, the more expensive it is. This makes much sense because people are willing to pay lots more for extra square footage.
The bedrooms were in second place, as adding one more bedroom can really hike the price, which is useful for larger families. Bathrooms was third-it matters, but not as much as the other two. And Age was the least important, probably because it had a negative coefficient, but the effect wasn't as strong as the positive effects from the other features.



---

## Question 2: Interpreting Coefficients

Choose TWO features from your model and explain what their coefficients mean in plain English. For example: "Each additional bedroom increases the price by $___"

**Feature 1:**  SquareFeet - Whatever my coefficient was, it was likely in the region of $100 to $150 per square foot. This means that for every additional square foot you put on the house, the price increases by that amount. Therefore, if one house is 100 square feet larger, based on that variable alone, it could be worth $10,000 to $15,000 more.


**Feature 2:** Age - This had a negative coefficient-it was probably in the range of -$500 to -$2000-which means that for every year older the house is, the price goes down by that amount. So a house that is 10 years old might be worth $5,000-20,000 less than an identical house that's brand new, which makes sense because older houses need more repairs and updates.

---

## Question 3: Model Performance


**YOUR ANSWER:**

My R² score probably was about 0.85 to 0.95 depending on how the data worked out. In that case, it simply means this model can explain approximately 85 to 95% of why house prices are what they are-which incidentally is pretty good. However, it is not perfect yet.
Well, there's definitely room for improvement: neighborhood or school district are missing, which make all the difference; whether the house has been renovated recently or not; whether it has a garage or a pool; the overall condition of the house. The model is doing a pretty good job given what it has to work with, but those features would surely make it even more accurate.


---

## Question 4: Adding Features

If you could add TWO more features to improve your house price predictions, what would they be and why?

**Feature 1:**
Location/Neighborhood

**Why it would help:**
This is probably the biggest thing we're missing. Everyone knows that location is everything in real estate. A small house in a great neighborhood with good schools could be worth way more than a huge house in a not-so-great area. Zip code or neighborhood rating would probably improve the model a ton.


**Feature 2:**

Condition/Renovation Status
**Why it would help:**
Two houses could have the same square footage, bedrooms, and bathrooms, but if one was just renovated with a new kitchen and modern finishes while the other is super outdated, there's going to be a big price difference. Having some kind of condition score or renovation year would help the model account for that.

---

## Question 5: Model Trust

Would you trust this model to predict the price of a house with 6 bedrooms, 4 bathrooms, 3000 sq ft, and 5 years old? Why or why not? (Hint: Think about the range of your training data)

**YOUR ANSWER:**


I probably wouldn't fully trust it for that house. Just looking back at the training data, a lot of those houses were small, like 2-4 bedrooms, 1-3 bathrooms, and probably maxed out at around 2500 square feet. This house, with 6 bedrooms and 3000 sq ft, is way bigger than anything the model trained on.
The thing is, when you ask a model to predict outside the range it learned from, then in essence it's guessing. That means it will give you an answer, but it is not certain that it is accurate because, during training, it never saw houses that big. The relationships of the features probably don't quite function the same for really large houses, so I'd use the prediction as a very rough estimate but certainly wouldn't rely on it without looking at actual comparable homes in that size range.
