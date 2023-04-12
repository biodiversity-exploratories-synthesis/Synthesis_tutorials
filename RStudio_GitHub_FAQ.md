# How to connect an existing Rproject to GitHub?

There are some tutorials around how to do this. In case you already tried those out, and don't succeeded (like me, usually), try this hack : 

It's way easier to connect an existing GitHub project to RStudio, and that's exactly what is done here. You rename your local project, create a new GitHub repository from within GitHub with the old name of your project, and create a new Rstudio project by cloning the existing GitHub repository.

1. Rename the folder you want to upload to git, e.g. by just adding "_backup"
2. Create a GitHub repository from within GitHub with the old (the original) name of your project
3. From within RStudio, create a new Rstudio project and chose "Select from version control". Select the GitHub folder you just created and connect this to your RStudio.
4. Once the connection between RStudio and GitHub stands, copy all your files from the "_backup" folder to the folder which is connected to GitHub. Copy all files BUT the RStudio project itself ("*.Rproj").


*file created by noschenk, last update 12-04-23*
