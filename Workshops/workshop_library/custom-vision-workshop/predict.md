# Part 2: Use the model

## Obtain keys and values

As with any service, we need to gather the keys and values to make our calls.

1. In the upper right corner of the Custom Vision interface, select the **Gear** icon for settings
1. Make a note of the **Key**, **Endpoint**, and **Project Id** values

> TIP: **Project Id** is the value on the left side of the screen

## Store the necessary credentials

Whenever you're writing code it's a best practice to never hard-code sensitive values, such as passwords, or any value which may change. This can lead to security breaches or code that's difficult to maintain. To create our application we're going to follow generally accepted best practices. To do this we'll use a library named [python_dotenv](https://github.com/theskumar/python-dotenv), which allows you to set environment variables with a text file.

1. In this project's root folder, create a new file named **.env**
1. Add the following values, replacing the placeholders

    ```bash
    ENDPOINT=<YOUR_ENDPOINT>
    KEY=<YOUR_PREDICTION_KEY>
    PROJECT_ID=<YOUR_PROJECT_ID>
    PUBLISHED_ITERATION_NAME=dogs
    ```

1. Save the file by selecting **File** > **Save**

## Install the packages

We'll be using two Python packages to support our project. The first we already introduced, **python-dotenv**. The next is the [Custom Vision client library (or SDK)](https://docs.microsoft.com/azure/cognitive-services/custom-vision-service/quickstarts/image-classification?tabs=visual-studio&pivots=programming-language-python), which you'll use to  make the predictions.

1. Create a new file named **requirements.txt**
1. Inside **requirements.txt**, add the following:

    ```bash
    python-dotenv
    azure-cognitiveservices-vision-customvision
    ```

1. Save the file by selecting **File** > **Save**
1. Open a new terminal window inside Visual Studio Code by selecting **Terminal** > **New Terminal Window**
1. Create a new Python environment and install the packages by running the following command:

    ```bash
    # On Windows
    python3 -m venv venv
    .\venv\Scripts\activate
    pip install -r requirements.txt

    # On Linux, WSL or macOS
    python3 -m venv venv
    source venv/bin/activate
    pip install -r requirements.txt
    ```

1. The packages will install.

## Create the program

With the setup work done, it's time to add your code! We'll break this down into a few sections.

1. Create a new file named **predict.py**

### Import the libraries

Most Python applications start by importing the required libraries, and our program will follow the same pattern.

1. Inside **predict.py**, add the following to import the necessary libraries:

    ```python
    # Predition client
    from azure.cognitiveservices.vision.customvision.prediction import CustomVisionPredictionClient
    # Key class for azure
    from msrest.authentication import ApiKeyCredentials
    # dotenv to load key
    from dotenv import load_dotenv
    # Import os to read environment variables
    import os
    ```

### Load the variables

Earlier we setup a few environment variables like our key and endpoint. Let's load those into memory.

1. At the end of **predict.py**, add the following code to load the environment variables

    ```python
    # Load the key and endpoint values
    load_dotenv()
    
    # Set the values into variables
    key = os.getenv('KEY')
    endpoint = os.getenv('ENDPOINT')
    project_id = os.getenv('PROJECT_ID')
    published_name = os.getenv('PUBLISHED_ITERATION_NAME')
    ```

### Perform the prediction

Now we can perform our prediction! We'll be using one of the images in the testing folder.

1. At the end of **predict.py**, add the following code to perform a prediction of dog breed

    ```python
    # Setup credentials for client
    credentials = ApiKeyCredentials(in_headers={'Prediction-key':key})
    
    # Create client, which will be used to make predictions
    client = CustomVisionPredictionClient(endpoint, credentials)
    
    # Open the test file
    with open('testing-images/american-staffordshire-terrier-10.jpg', 'rb') as image:
        # Perform the prediction
        results = client.classify_image(project_id, published_name, image.read())
    
        # Because there could be multiple predictions, we loop through each one
        for prediction in results.predictions:
            # Display the name of the breed, and the probability percentage
            print(f'{prediction.tag_name}: {(prediction.probability):.2%}')
    ```

## Run the program

With the program created, let's run it and see what happens!

1. Save all files by selecting **File** > **Save All**
1. Return to the terminal inside Visual Studio Code by selecting **View** > **Terminal**
1. Run the following command to execute the program

    ```bash
    python predict.py
    ```

1. You should now see the following output:

    ```bash
    american-staffordshire-terrier: 97.11%
    german-wirehaired-pointer: 1.46%
    australian-shepherd: 0.97%
    buggle: 0.46%
    shorkie: 0.00%
    ```

    > **Note**: Your percentages may not exactly match those above

## Challenge

Now that you know how to create a model, try a different set of images. You can use your camera to create an image set of things like food or plants, or use Creative Commons Licensed images from the web. Can you tell the difference between different types of noodles? Leaves? dumplings? fish?
