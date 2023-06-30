# Folder Text Replacement Script

This PowerShell script replaces specified text in JavaScript, CSS, and HTML files within a given folder path.

## Usage

## 1. Set the desired folder path where the script will look for files to modify:

```powershell```
$folderPath = "C:\Users\abmou\Documents\GitHub\Edukids\src"

## 2. Specify the old text that you want to replace:

```powershell```
$oldText = "Flexwijs"

## 3. Define the new text that will replace the old text:
```powershell```
$newText = "edukids"

## 4. Get all JavaScript files within the folder path:
```powershell```
$jsFiles = Get-ChildItem -Path $folderPath -Filter "*.js" -File -Recurse

## 5. Get all CSS files within the folder path:
```powershell```
$cssFiles = Get-ChildItem -Path $folderPath -Filter "*.css" -File -Recurse

## 6. Get all HTML files within the folder path:
```powershell```
$htmlFiles = Get-ChildItem -Path $folderPath -Filter "*.html" -File -Recurse

## 7. Combine JavaScript, CSS, and HTML files into a single array:
```powershell```
$files = $jsFiles + $cssFiles + $htmlFiles

## 8. Iterate through each file and replace the text:
```powershell```
foreach ($file in $files) {
    $content = Get-Content -Path $file.FullName
    $updatedContent = $content -replace $oldText, $newText
    $updatedContent | Set-Content -Path $file.FullName
}

## Explain

The script retrieves all JavaScript, CSS, and HTML files within the specified folder and its subdirectories. It replaces the specified text with the new text in each file.

Example
For example, suppose you have a folder path set to "C:\Users\abmou\Documents\GitHub\Edukids\src". The script will find all JavaScript, CSS, and HTML files within this folder and its subdirectories. It will replace the text "Flexwijs" with "edukids" in each file.

Please note that this script assumes that you have PowerShell installed on your system and have the necessary permissions to modify the files in the specified folder.

Feel free to modify and adapt this script according to your specific requirements.