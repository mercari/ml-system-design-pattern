# Model load pattern

## Usecase
- When update cycle of a model is more frequent than server image update.
- When you want to reuse a server image for serving multiple models.

## Architecture
While productionizing an ml service on a cloud platform (or on containers) becomes a common practice, it is still an important consideration to manage and version machine learning model along with its server image. By building server (or container image) and model file separately, you may be able to decouple the management of the model and the server. In the model-load pattern, you build and save the prediction server image and model file separately, making the image light-weight with respect to size. It is also possible and responsible, to design the image for common use. Such a design allows reusing the same image on various prediction models, making this pattern highly effective when your models are compatible with the same image.<br>
To release a prediction service using this pattern, the prediction server needs to be deployed first into the platform, and then it downloads the model file as its initial task, before starting the prediction process. You may consider using an environmental variable to configure which model needs to be run on the server.<br>
A difficulty of the pattern is to manage dependent library for the models. You are required to match the library versions that the model uses and the ones that is installed in the image. It will be needed to make a table of supported libraries for each image and models, thus resulting in increase of operation.

## Diagram
![diagram](diagram.png)


## Pros
- Separate model versioning and image versioning.
- Reuse of server image.
- Light image size.
- Change management of server image becomes easier.

## Cons
- It may take longer to start the service. The server although up should be treated as unhealthy until the model load completes.
- A new requirement of matching supported library versions between images and models is applicable for this pattern.

## Needs consideration
- Dependent version management of server image and model file.

## Sample
https://github.com/shibuiwilliam/ml-system-in-actions/tree/main/chapter3_release_patterns/model_load_pattern