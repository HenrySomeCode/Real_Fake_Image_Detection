# Real/Fake Image Detection

## What's the problem, and Why is it important?

I once received a topic from a financial company. It is "Real/Fake Money Transfer Screenshot Detection From Mobile Banking App ."That company has recently received many fake screen captures of money transferring from a group user, say group 2. These users use original screen captures from users that paid, say group 1, and somehow turn it into their screen capture with the name, id, Etc, replaced.

That's why detecting real/fake images is essential, especially if the image is manipulated from an original image. 

## What will I do?

The given data from the financial company is imbalanced. Moreover, using the original data may cause several problems related to the private information of that company. I will not upload the original data here. Instead, I will use available data for real/fake image detection. Also, I'll try to make it imbalanced so that I have way more realistic data.

For handling imbalanced data, in my opinion, we have some methods below:

* Using the right metrics to evaluate the model: Do not use "accuracy ."Instead, use something like Precision, Recall, F1 score, or AUC.
* Resample data to make it balanced:  
  * Random undersampling: Balancing the data by reducing the size of the abundant class to the same size as the rare class. This wouldn't work when the quantity of rare class is small. This is my case, so I will not use this.
  * Random oversampling: Balancing the data by increasing the size of the rare class to the size of the abundant class. New samples can be created by using the following:
    * Repetition: Duplicating rare samples doesn't make much sense, so I don't prefer this one
    * SMOTE: Generate samples using features of neighbor samples. This method is less popular with images as much as its popularity when dealing with structured data. But it does help so I may consider this later.
* Esamble different models: I suggest this is the method that I'm looking for, by dividing the abundant class into parts that each is equal to the rare class. We train several models on both each abundant class part and the rare class. The final result is combined from different models. This method may have a drawback as it needs time to mix the results together, but this project doesn't need such real-time, so it's pretty decent.
* Re-design model: by designing a loss function that penalizes the wrong classification of the rare class more than the one of the abundant class, I might get a better model that suits imbalanced data.   

## Data

## Results

## Cons & Pros

## What can be done to improve the model?


