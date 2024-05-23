# Machine Learning
**May 23, 2024**

## The Math Behind Machine Learning
Machine learning attempts to predict an outcome given some data.

The mathematical equivalent of this is a function that takes the data as input and outputs the result.

For example, a machine learning model with four inputs would look like:

f(a, b, c, d) = w<sub>a</sub>a + w<sub>b</sub>b + w<sub>c</sub>c + w<sub>d</sub>d + C

Each input is multiplied by a weight that determines how much it affects the output. For example, if `b` had no effect on the output of `f(a, b, c, d)`, w<sub>b</sub> would be 0.

C is a constant that moves the graph of the function up or down. It doesn't depend on the input.

#### What's wrong?
This takes in numerical values, and outputs a number, so more work is required to apply this to non-numerical problems.

## Training
Each weight must be determined before the model is useful. The process of determining these weights is called "training".

Training looks at past data and outcomes to find weights to minimize the error between the predicted outcome and actual outcome.

### Labelling
*Labelling* is the process of taking input and annotating it to provide additional training information.

For example, if a model was being trained to predict whether an image has a dog or a cat in it, each training image would be labelled either "dog" or "cat" so the model could associate the characteristics of the image with a dog or cat.

### Overfitting
*Overfitting* is a problem that occurs when a model is trained to predict the training data too accurately, and can't adapt to variances in input.

![A plot of two sets of data with a green line showing an overfit model accurate for one set, and a black line showing a model accurate for both sets.](https://elitedatascience.com/wp-content/uploads/2017/09/Overfitting-Data-Points.png)

(Image from `elitedatascience.com`)

> This image illustrates two sets of data (red and blue dots), a model that is overfit to one set of data (the green line), and a model accurate for both sets (the black line).

A model that is overfitted to the training data will perform exceptionally well on the training data but will perform poorly when tested with new data.

Overfitting occurs because a model associates *noise* present in the training data with the output. If this noise isn't present in the real data, the model's accuracy will be reduced significantly.

> *Noise* is the term for trends in data with no relationship to the output, such as outliers or measurement errors.

For example, if a model was trained to detect a pedestrian to use in an emergency braking system for cars, it would be overfit if it was trained only to detect pedestrians during the day.

It would look for characteristics only found during the day, such as the shadow pedestrians make with the sun. Once the model was deployed in the real world, it would miss pedestrians during a cloudy day, or during the night when it found a different shadow from the car's lights.

#### Avoiding Overfitting
There are several techniques to avoid overfitting.

For example, the input data could be randomly split into three datasets: Training, Validation, and Testing.

The model is trained with the training dataset, and its function is verified with the testing dataset. The validation dataset is used to verify the model isn't overfit.