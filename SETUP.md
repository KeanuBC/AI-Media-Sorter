# AI Media Sorter - Setup & Installation

## 1. Requirements

- Python 3.9 or newer recommended
- Pillow
- OpenCV
- Tkinter

Tkinter is normally included with Python on Windows.

## 2. Install Dependencies

Open Command Prompt or a terminal and run:

```bash
python -m pip install Pillow opencv-python
```

If you are using a Python installation without Tkinter, install the appropriate Tkinter package for your operating system.

## 3. Project Files

A simple project structure:

```text
AI-Media-Sorter/
├── ai_media_sorter.py
├── README.md
├── SETUP.md
└── LICENSE
```

## 4. Running the Program

Open a terminal in the project folder and run:

```bash
python ai_media_sorter.py
```

The program will ask you to select two folders.

### Input Folder

Choose the folder containing the images and videos you want to scan.

The program also scans files inside its subfolders.

### Output Folder

Choose a separate folder where the sorted copies will be stored.

**Important:** Do not choose a folder inside the input folder. The program could encounter its own output while scanning.

## 5. Understanding the Results

Each supported file receives a score based on available clues.

| Score | Output Folder |
|---|---|
| 70+ | AI |
| 40–69 | Likely_AI |
| 20–39 | Unsure |
| 0–19 | Likely_Human |

The program creates these folders automatically.

## 6. File Handling

- Original files are not moved or deleted.
- Sorted files are copied to the output directory.
- Original subfolder organization is preserved.
- Existing files with matching destination names may be overwritten.

Keep backups of important files and use an empty output folder when possible.

## 7. Troubleshooting

### Pillow or OpenCV Missing

Run:

```bash
python -m pip install --upgrade Pillow opencv-python
```

### Tkinter Not Found

Your Python installation may not include Tkinter. Install the operating system's Tkinter package or use a standard Python installation that includes it.

### Video Files Are Not Being Scanned

Check that the video uses one of the supported extensions:

- MP4
- MOV
- AVI
- MKV

### No Files Appear in the Output

Make sure you selected the correct input and output folders and that the input folder contains supported image or video files.

## 8. Detection Disclaimer

AI Media Sorter does not definitively identify AI-generated media. Its scoring system uses metadata, filenames, image properties, and video frame rates as indicators.

Treat the results as estimates and manually review important files.
