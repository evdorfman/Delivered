# Delivered

A small tool for logging finished video deliverables into Smartsheet.

Pick one or more video files (or a whole folder) and it reads each file's details, then gives you tab-separated rows to paste straight into a Smartsheet sheet.

## Use it

1. Open `delivered.html` in Chrome, Edge, or Safari (double-click it; nothing to install).
2. Fill in **Same for every file in this batch**: Request Name, Assigned To, dates, workstreams, Business Unit, etc. These are remembered for next time.
3. Paste the **folder path** you're adding from so File Path is filled in.
   - Mac: right-click the folder in Finder, hold **Option**, choose **Copy "…" as Pathname**.
   - Windows: **Shift + right-click** the folder, choose **Copy as path**.
4. Drop videos or a folder onto the page, or use **Choose files** / **Choose folder**.
5. Paste each Frame Link into its row (click any cell to edit it), then **Copy rows**.
6. In Smartsheet, click the **Task Name** cell of the first empty row and paste. Rows come out in the tracker's 27-column order.

Videos never leave your computer; the page only reads their headers.

## How each column is filled

| From the file | Batch field (typed once) | Per file |
| --- | --- | --- |
| Task Name (file name without extension) | Request Name | Deliverable Name |
| Project Name (first four `_` parts of the file name, e.g. `26_LVE_BXPW_BREITIsBack`) | Status, Assigned To | Frame Link |
| Aspect Ratio (`16x9`, `9x16`, `1x1`, `4x5`…, corrected for rotation/anamorphic) | Actual Start / End Date (MM/DD/YY) | |
| Quality (4K / HD / SD from resolution) | Frame Password, Number of Revisions/Cuts, Notes | |
| Length of Video (bucket; options editable on the page) | Distribution Platform, Deliverable Type | |
| Actual Length of Video (HH:MM:SS) | Deliverable Workstream, Workstream, Business Unit | |
| File Path (pasted folder + subfolders, optionally the file name) | Eleven Labs Use, Contains AI, Green Screen Use | |
| SRT file delivered? (`Yes` when a same-named `.srt` is beside the video) | Sheet Name | |

Any cell can be overridden in the table before copying.

MOV / MP4 / M4V (H.264, HEVC, ProRes, etc.) are parsed directly, so large files and ProRes work even though browsers can't play ProRes. Other formats fall back to what the browser can read.

## Why paths need pasting

Browsers don't let web pages see where a file lives on disk. The pasted folder path is combined with subfolders inside it to build File Path.
