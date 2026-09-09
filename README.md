# Time and season - aware wallpaper tool

Automatically change your wallpaper folder to match the season and time of day!

### Instructions:

<<<<<<< HEAD
Create a master folder to store all wallpaper images and folders. This can have any name.
=======
> [!IMPORTANT]
> Only tested on MacOS. Parts of the application will currently not function correctly outside of MacOS. The tool is still usable on other platforms however there will be some delay between running the tool and the wallpaper correctly updating.

1. Create a master folder to store all wallpaper images and folders. This can have any name.
>>>>>>> 1746d2f (Fix install.sh to curl executable from Github)

2. Within the master folder, create the following sub-folders or run the below shell script inside the master folder:

/Spring-Day  
/Spring-Night  
/Summer-Day  
/Summer-Night  
/Autumn-Day  
/Autumn-Night  
/Winter-Day  
/Winter-Night

Important: Each sub-folder should contain a file called name.txt which contains the name of the folder. This is because the current wallpaper folder will be renamed to `Active` by the tool.

```
folders=("Spring-Day" "Spring-Night" "Summer-Day" "Summer-Night" "Autumn-Day" "Autumn-Night" "Winter-Day" "Winter-Night")

for folder in "${folders[@]}"; do
    mkdir "$folder"
    cd "$folder"
    echo "$folder" >> name.txt
    cd ..
done
```

3. Once these folders and files have been created, rename one of the folders to `Active` and set it as your wallpaper folder in your system's settings.

4. Go back to the initial folder from github and run `./install.sh`.

This will install the compiled binary to `/usr/local/bin` and add a cron job that runs the program once an hour and update your wallpaper folder if needed.

You can also enter `wallpaper` in the terminal to update the wallpaper folder manually.

> [!TIP]
> The date intervals for the seasons are stored in `seasons.json` in your wallpaper directory after running `install.sh`. These dates can be edited to adjust the season transitions for the program.

### Uninstallation

To uninstall the program, run `./uninstall.sh` from the original install folder. Or enter this in the terminal:

```
rm /usr/local/bin/wallpaper
```
