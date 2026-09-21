 Database Folder Matcher

# 

# A Windows Forms (VB.NET) app that loads a SQLite `.db` file, scans its main table into a fast virtual list, and matches folders on disk with the database by name, by ID, or both.

# 

# \## Features

# 

# \- Load any `.db` (SQLite) file and scan it into a virtual ListView (handles large tables)

# \- Live search on the scanned list (top search box)

# \- Add one or more scan locations and tick/untick them from the Database menu

# \- Match folders on disk:

# &#x20; - By Name (exact + fuzzy: ignores case, separators, roman numerals, acronyms)

# &#x20; - By ID (folder name equals App ID column)

# &#x20; - Filter By Both (name AND/OR id)

# \- Tree view of matches with subfolders, match counts, and tooltips

# \- Tree search box (bottom) with nested-subfolder search and yellow highlight

# \- Group combo (CPY, CODEX, RUNE, SKIDROW, etc.) for release-group folder scan

# \- Tree right-click menu: Open, Save As Zip, Copy/Move/Rename, New Subfolder, Delete to Recycle Bin, Copy Path/Name, Properties, Expand/Collapse All

# \- Remembers database path, scan folders, and group selection between runs

# \- About dialog in the top menu

# 

# \## Requirements

# 

# \- Windows 10/11 (x64)

# \- \[.NET 10 SDK](https://dotnet.microsoft.com/download) (project targets `net10.0-windows`, `UseWindowsForms=true`)

# \- NuGet package: `Microsoft.Data.Sqlite 10.0.12` (restored automatically on build)

# \- A SQLite `.db` file with at least one user table containing a name column and/or an ID column

# 

# \## Getting Started

# 

# ```powershell

# dotnet build WinFormsApp1.slnx

# dotnet run --project WinFormsApp1\\WinFormsApp1.vbproj

# ```

# 

# Or open `WinFormsApp1.slnx` in Visual Studio and press F5.

# 

# \## How To Use

# 

# \### 1. Load the database

# 

# 1\. Go to `Database > Click To Load DataBase`.

# 2\. Select your `.db` file. The window title shows the loaded file name.

# 

# \### 2. Add scan locations

# 

# 1\. Go to `Database > Location For Scan`.

# 2\. Pick a folder. Click Yes to add more folders.

# 3\. Added folders appear under the Database menu with a tick. Untick any folder to exclude it from matching.

# 

# \### 3. Scan the database

# 

# 1\. Press `Scan`. The progress bar moves 0 → 100 and the table name/row count appears in the title.

# 2\. Press `Stop` anytime to cancel.

# 

# \### 4. Search the list

# 

# \- Type in the top search box (`RichTextBox1`, with `x` button to clear). The list filters live with match highlighting.

# 

# \### 5. Match folders

# 

# \- `By Name` — matches disk folder names against the DB name column (fuzzy).

# \- `By ID` — matches disk folder names against the DB ID column (exact).

# \- `Filter By Both` — keeps folders matching name and/or ID, labelled `Name`, `Name\~`, `ID`, `Name+ID`.

# \- Result appears in the tree as `location (count)` → matched folders with subfolders.

# 

# \### 6. Search the tree

# 

# \- Type in the bottom search box (`TextBox1`, 2+ characters). It searches matched folders AND nested subfolders, keeps matching branches, and highlights the query.

# \- Clearing the box restores the full tree.

# \- `Collapse` checkbox controls auto-expand behaviour.

# 

# \### 7. Group scan

# 

# \- Pick a group from the combo (e.g. `CODEX`, `RUNE`). It scans ticked locations for folder names containing that tag.

# \- Select the empty entry to go back to the database matches.

# 

# \### 8. Tree right-click actions

# 

# \- `Open Folder` — open in Explorer (same as File > Open).

# \- `Save As Zip...` — zip the selected folder (same as File > Save As).

# \- `Copy/Move Folder To...`, `Rename...`, `New Subfolder...`, `Delete to Recycle Bin...`.

# \- `Copy Full Path`, `Copy Folder Name`, `Properties`, `Expand/Collapse All`.

# 

# \### 9. File menu

# 

# \- `New` — clears list, tree, and searches (asks to Stop first if busy).

# \- `Open` — opens the selected tree folder in Explorer.

# \- `Save As` — zips the selected tree folder.

# \- `Exit` — closes the app (locations are auto-saved).

# 

# \## Where Settings Are Stored

# 

# Scan folders, tick states, database path, and group selection are saved to:

# 

# ```

# %AppData%\\WinFormsApp1\\locations.txt

# ```

# 

# Delete this file to reset.

# 

# \## Project Structure

# 

# ```

# WinFormsApp1.slnx

# WinFormsApp1/

# &#x20; Form1.vb            Main logic (scan, filter, tree, preview, menus)

# &#x20; Form1.Designer.vb   UI layout

# &#x20; Form1.resx

# &#x20; ApplicationEvents.vb

# &#x20; WinFormsApp1.vbproj

# ```

# 

# \## Developed By

# 

# AMIT



