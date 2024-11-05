# Automated File Organization System Using Python

**Project Overview**

The Automated File Sorter is a Python tool that organizes file directories by automatically sorting files into designated folders based on file type. Ideal for maintaining an uncluttered workspace, this script categorizes files—such as **.json**, **.txt**, **.PNG**, and **.xlsx**—into respective folders, saving you time and keeping directories tidy.

This project leverages Python’s **os** and **shutil** libraries to perform directory management and file movement, making it especially useful for users who frequently work with various file types in a single directory.

**Key Features**

* **Automated Sorting:** Organizes files into folders by file type, keeping directories neat.

* **Customizable Folders:** Easily add support for new file types by modifying the script.

* **Streamlined Management:** Saves time by automating the sorting process and eliminating manual categorization.

**How It Works**

**1) Define the Directory Path:** Set the directory you want to organize by specifying the **path** variable.

**2) Create Folders for Each File Type:** The script checks for existing folders labeled by file type (e.g., "json files", "image files") and creates them if they don’t already exist.

**3) Sort Files into Folders:** Files are then moved into their respective folders based on extensions such as **.json**, **.txt**, **.PNG**, and **.xlsx**.

**Code Explanation**

**1. Imports and Path Setup**

* Import the necessary libraries and define the target directory path.

      import os
      import shutil
      path = r"C:/path/to/your/directory"

* **os:** Provides access to operating system functions for directory management.

* **shutil:** Offers high-level file operations, like moving files.

**2. Folder Creation**

* Define folder names and check if they exist in the specified path. If they don’t, the script will create them.

      folder_names = ['json files', 'image files', 'text files', 'excel files']
      for folder in folder_names:
          if not os.path.exists(path + folder):
              os.makedirs(path + folder)

This loop ensures that folders for each file type are available. If a folder doesn’t exist, it’s automatically created.

**3. File Sorting Logic**

* Loop through each file in the directory and move it to the appropriate folder based on its file extension.

      file_names = os.listdir(path)
      for file in file_names:
          if ".json" in file and not os.path.exists(path + "json files/" + file):
              shutil.move(path + file, path + "json files/" + file)
          # Similar logic for other file types

This part of the code identifies files by extension and relocates them to their designated folders. For other file types, similar **elif** statements can be added to customize the script.

**Customization**

To add support for additional file types:

**1) Add a Folder Name:** Include a new folder in the **folder_names** list.

**2) Add an Extension Check:** Add an **elif** clause in the sorting logic to check for the new file extension and move the file to its corresponding folder.

**Conclusion**

The Automated File Sorter provides a quick and effective solution for managing directories with mixed file types. By running this Python script, users can effortlessly maintain organized directories, save time on manual sorting, and enhance productivity in any workspace.




















