# Setting Up a PySpark Notebook Using Docker

This guide will walk you through setting up a PySpark notebook environment using Docker.

## Prerequisites

- Docker installed on your machine

## Steps
Step 1: Pull the Docker Image

Start by pulling the jupyter/all-spark-notebook image, which is packed with Spark 3.5.0.

1. **Pull the Docker Image**

    Start by opening the commandline. Pull the jupyter/all-spark-notebook image by issuing the following command:
    
    ```bash
    docker pull jupyter/all-spark-notebook:spark-3.5.0
    ```

2. **Set Up Your Workspace**

    Create a directory for the sparkdata on your device. For example:

    ```bash
    /Users/jasper.brancart/sparkdata:/sparkdata
    ```

3. **Run the Docker Container**

    Run the Docker image and make sure to map it to the directory we created in step 3.
    
    ```bash
    docker run -d -P --name notebook -v {YOUR_FOLDER_HERE} jupyter/all-spark-notebook:spark-3.5.0
    ```


4. **Locate your notebook**

    Check what port the Notebook is hosted to
    
    ```bash
    docker port notebook 8888
    ```

5. **Access your notebook**

    Issue the following command to fetch your security token.

   ```bash
   docker logs --tail 3 notebook
   ```
  *Update the default port (8888) in the above URL with the port you found in step 4*

  (ie. http://127.0.0.1:32776/lab?token=YOUR_TOKEN)
   
   

## Conclusion

You've successfully set up a PySpark notebook environment using Docker. Happy coding!
