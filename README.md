# Mutli Branch Pipeline Practice.

In this repo I have done practicing continuous integration of mutli branch pipeline in jenkins.

What I did was:
- Created a VM in Google Cloud
- Installed docker on it
- Ran Jenkins as a Docker Container.

I will walkthrough you so that you can aslo build Continuous intergation of mutli branch pipeline

For practicing you need 
- A application, in my [java-maven-application](https://github.com/Hemanth42d/java-maven-app-learning-jenkins.git)
- Create a server in a cloud service (aws, google cloud, azure)
- Install docker in it [If you don't know how click here](https://github.com/Hemanth42d/build_with_docker1/blob/main/readme.md)
- And run Jenkins as a docker container [don't know how click here](https://github.com/Hemanth42d/docker_in_jenkins.git)

After completion of above steps we need to create a job in jenkins of type **Mutli Branch Pipeline** and it can be done via UI, click on + New Item in the side dashboard and fill the name and select **Multi branch pipeline**
Then you will be redirected to a UI of **Multi branch pipeline** and Under Branch Source click on **Add Source**
<img width="1899" height="869" alt="Screenshot from 2025-08-21 15-06-04" src="https://github.com/user-attachments/assets/d5dbc86c-10d9-4034-a81a-47769f9e3682" />

Then you need to provide your git repo link and don't forget to add github credentials in credentials section in jenkins manage.
After giving the repo link you need to select the branches you need to build the pipeline for as shown in the images under Discover Branch.
<img width="1899" height="869" alt="Screenshot from 2025-08-21 15-06-34" src="https://github.com/user-attachments/assets/86e24c21-d8c1-4322-8331-e2e4164a7cf7" />
Select the fliter name by regular expression in the dropdown option which means based on the expression you provide that branches will be dynamically added for the pipelines
Example: 
1) feature/  --> means adds all branches that starts with features expression
2) bug-fix/  --> means adds all branches that starts with bug-fix expression
3) .* --> for all branches.

And the last thing is under Build Configuration select the option **Mode by Jenkinsfile** and under script path select **Jenkisfile**(It is dynamic variable you can name it what ever you want but best practice is to name it Jenkinsfile defualt convention)
<img width="1899" height="869" alt="Screenshot from 2025-08-21 15-08-07" src="https://github.com/user-attachments/assets/344c5b59-d898-45ca-baf0-b94afef4361c" />

After that click on save and you will be redirected to main page of Multi branch pipeline and click on **scan Multi branch pipeline** in the sidebar and the pipeline will starts its work based on the jenkicfile content.
After successful you will see something like this 
<img width="1899" height="869" alt="Screenshot from 2025-08-21 15-23-47" src="https://github.com/user-attachments/assets/da5e7f9e-1004-4963-9ee1-c5ecd750f9c4" />
<img width="1899" height="869" alt="Screenshot from 2025-08-21 15-23-58" src="https://github.com/user-attachments/assets/fc627e19-1ece-45dd-bcbd-c6c17e1dbb40" />

If you want to dynamically add the branches for pipeline then you should have filled the regular expression with the .* and when you add another branch it will be dynamically adds the branch for the next scan of multi branch pipeline as shown in image

<img width="1899" height="869" alt="Screenshot from 2025-08-21 15-25-01" src="https://github.com/user-attachments/assets/1e567fca-2ec8-4c88-a0f7-18ce188df1cf" />

You can see the text **Processed 3 Branches** at the bottom of the image
After sucessfull completion you will se something smilar to above provided image with three branches

<img width="1899" height="869" alt="Screenshot from 2025-08-21 15-24-52" src="https://github.com/user-attachments/assets/b5da6bcb-df53-45a3-ba00-f2cb9b60fbe1" />




