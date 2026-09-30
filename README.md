# Delivered

A small tool for logging finished video deliverables into Smartsheet.

Pick one or more video files (or a whole folder) and it reads each file's details, then gives you tab-separated rows to paste straight into a Smartsheet sheet.

## Use it

1. Open `delivered.html` in Chrome, Edge, or Safari (double-click it — nothing to install).
2. Optional: type the **project name** (otherwise the folder name is used).
3. Paste the **path of the folder** you're adding from, so the File location column is filled in.
   - Mac: right-click the folder in Finder, hold **Option**, choose **Copy "…" as Pathname**.
   - Windows: **Shift + right-click** the folder, choose **Copy as path**.
4. Drop videos or a folder onto the page, or use **Choose files** / **Choose folder**.
5. Fix any cell by clicking it, pick which columns you want, then **Copy rows**.
6. In Smartsheet, click the first empty cell in the first column and paste.

Videos never leave your computer; the page only reads their headers.

## What it fills in

| Field | Source |
| --- | --- |
| Project name | Typed in, or the name of the folder you added |
| File name | The file |
| File location | Pasted folder path + any subfolders |
| Length | Container header (HH:MM:SS, MM:SS, timecode, or seconds) |
| Aspect ratio | Display size, corrected for rotation and anamorphic pixels, snapped to standard ratios |
| Orientation, Resolution, Frame rate, Codec, File size, Date modified | Optional extra columns |

MOV / MP4 / M4V (H.264, HEVC, ProRes, etc.) are parsed directly, so large files and ProRes work even though browsers can't play ProRes. Other formats (WebM, MKV, MXF…) fall back to what the browser can read; anything missing can be typed in.

## Why paths need pasting

Browsers don't let web pages see where a file lives on disk. The pasted folder path is combined with subfolders inside it to build the location.
