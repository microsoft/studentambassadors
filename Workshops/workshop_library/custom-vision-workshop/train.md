# Part 1: Train your model

## Create the project

A project is a custom vision model. It's used to label images with the appropriate tag (or category), and perform the training. Let's start by creating a project.

1. Navigate to [Custom Vision](https://www.customvision.ai) and sign in
1. Select **New Project**
1. Enter **Dog Classification** for the project name
1. Next to Resource, select **create new** to create a key in Azure for the service
1. On the **Create New Resource** enter the following information
    - **Name**: **custom-vision**
    - **Subscription**: Choose your student subscription
    - **Resource Group**: Select **Create New**
        - Enter **custom-vision** for the name, and choose a location near you, then select **Create resource group**
        - Select the **custom-vision** resource group you created
    - **Kind**: **CustomVision.Training**
    - **Location**: The same location you chose earlier
    - **Pricing Tier**: **F0** for the [free tier](https://docs.microsoft.com/azure/cognitive-services/custom-vision-service/limits-and-quotas)
    - Select **Create resource**
1. For **Project Types** select **Classification**
1. For **Classification Types** select **Multiclass**, as our dogs will only have one breed
1. For **Domains** select **General**
1. Select **Create project**

## Upload images

Once the project is created it's time to upload images. These images are used to train the model.

> **Tip**: As a general rule, the more images you can use to train a model the better. You want to include as much variety in the images as possible, including different lighting, angles, and settings.

1. Select **Add images**
1. Navigate to **training-images**
1. Select all the images marked as **american-staffordshire-terrier** in the folder, and select **Open**
1. Enter **american-staffordshire-terrier** for the tag and select **Upload 8 files**
1. Select **Done**
1. Repeat the above steps for the remaining breeds:
    - **australian-shepherd**
    - **buggle**
    - **german-wirehaired-pointer**
    - **shorkie**
1. Select **Train** to open the training dialog
1. Leave **Quick Training** selected and select **Train** to begin the training process

> **Note**: Training the model will take a couple of minutes.

## Test the model

With the model trained, let's see how well it works. It's important to use images which weren't used to train the model. After all, if the model has already seen the image it's going to know the answer.

1. Select **Quick Test**
1. Select **Browse local files**
1. Navigate to **testing-images** and select one of the dog images
1. Select **Open**
1. Notice the **tag** and **probability** scores

## Publish model

The goal of creating a model in Custom Vision is to use it in different applications. To access it from outside of the Custom Vision website it needs to be published.

1. In the 'Performance' tab, select **Publish**
1. Enter **dogs** for **Model name**
1. Select the **resource** you created for **Prediction resource**
1. Select **Publish**
1. Select **Prediction URL** to view the endpoint address
1. Copy the value in the grey textbox under **If you have an image file** and paste it somewhere locally where you can find it later
1. Select **Got it**

Now you're ready to use this model in an application. Continue to [part 2](./predict.md)