# Tutorial: Creating a Cooked Project for *FNaF: Security Breach*

## Introduction  
This guide will walk you through creating a Cooked Project for *FNaF: Security Breach* using Unreal Engine 4.27.2.

---

## Requirements  
1. **Security Breach's actual game files (get them from steam, if you do not own the game you should not be here)**
2. **SBRUIN Blank Project** – The files in this repo are the blank project
3. **Unreal Engine 4.27.2** – [Download here](https://store.epicgames.com/download)  
4. **UE 4.27.2 Cooked Asset Support Patch** – [Download here](https://github.com/LunerLA2/Unreal-Engine-4.27.2-CAS-Patch)  
5. **Visual Studio 2022** – [Download here](https://visualstudio.microsoft.com/downloads/)  
6. **Repak** – [Download here](https://github.com/trumank/repak/releases/)  
7. **.NET Framework** – [Download here](https://go.microsoft.com/fwlink/?linkid=2203306)  

---

## Instructions  

### 1. **Prepare the Blank Project**  
1. Download `SBRUIN-Blank-4.27.rar` and extract it.  
2. Download Repak from the link above and open a command prompt in its location.  

---

### 2. **Unpack the Game’s Files**  
Edit and run the following commands in the command prompt:  

#### First Command  
```bash
repak.exe -a 0x85F7D4007015493ED0359C9007266038F8F7B1F96988F19A610103874CC95286 unpack -f -o "[path_to_blank_project]" "[path_to_game_pak_folder]\fnaf9\Content\Paks\fnaf9-WindowsNoEditor.pak"
```  

#### Second Command  
```bash
repak.exe -a 0x85F7D4007015493ED0359C9007266038F8F7B1F96988F19A610103874CC95286 unpack -f -o "[path_to_blank_project]" "[path_to_game_pak_folder]\Chowdafnaf9-WindowsNoEditor.pak"
```  
Wait for each progress bar to finish before proceeding.

---

### 3. **Organize the Project Folder**  
1. Navigate to your Blank Project folder.  
2. Inside the `fnaf9` folder, move the following files into the main Blank Project folder:  
   - `Config`  
   - `Content`  
   - `Plugins`  
   - `AssetRegistry.bin`  
3. When prompted, click **Skip these files**.

---

### 4. **Generate Visual Studio Files**  
1. Right-click on `fnaf9.uproject` in the Blank Project folder.  
   - On Windows 11, you may need to select **Show More Options**.  
2. Select **Generate Visual Studio Project Files**.  
3. Ensure the engine version is set to **4.27** and click **OK**.

---

### 5. **Rebuild the Project**  
1. Open `fnaf9.sln` with Visual Studio 2022.  
2. In the **Solution Explorer** (right side), right-click on `fnaf9` and select **Rebuild**.  

---

### 6. **Modify Configuration Settings**  
1. Go to the `Config` folder in the Blank Project folder.  
2. Open `DefaultEngine.ini` in a text editor.  
3. Locate line **237** and paste the following:  
   ```ini
   cook.AllowCookedDataInEditorBuilds=True  
   s.AllowUnversionedContentInEditor=1  
   ```  
4. Save the file.

---

### 7. **Open the Project**  
1. Open `fnaf9.uproject`.  
2. If prompted to upgrade files, select **No**.  

---

## Congratulations!  
You now have a Cooked Project. You can browse and even edit some of the files.  

---

### Credits  
This guide was inspired by resources from the *FNaF Technical Discord*.  
