# AI Media Sorter

A Python tool that scans images and videos and estimates whether they may be AI-generated. Files are scored using metadata, filenames, image properties, and video frame rates, then copied into categorized folders.

## Features

- **Automatic folder scanning:** Select an input folder to scan, including its subfolders.
- **AI metadata detection:** Looks for AI-related keywords in image metadata.
- **Filename analysis:** Checks for common AI-generation naming patterns.
- **Image analysis:** Examines image dimensions, file size, and EXIF information.
- **Video analysis:** Checks video frame rates for potential clues.
- **Automatic scoring:** Assigns each file a score based on detected indicators.
- **Categorized sorting:** Copies files into folders according to their scores.
- **Folder structure preservation:** Recreates the original subfolder structure in the output directory.

## Supported Formats

**Images**
- PNG
- JPG
- JPEG
- WEBP

**Videos**
- MP4
- MOV
- AVI
- MKV

## Rating Categories

| Score | Category |
|---|---|
| 70 or higher | AI |
| 40–69 | Likely_AI |
| 20–39 | Unsure |
| Below 20 | Likely_Human |

These categories represent estimates, not confirmed results.

## Installation

Install the required Python packages:

```bash
python -m pip install Pillow opencv-python
```

Tkinter is generally included with standard Python installations.

See [SETUP.md](SETUP.md) for installation and usage instructions.

## Usage

Run the script:

```bash
python ai_media_sorter.py
```

Two folder selection windows will appear:

1. Select the input folder containing the media you want to scan.
2. Select the output folder where sorted copies should be saved.

The program will scan the input folder and print each supported file's score and assigned category in the terminal.

## Output Structure

The program creates four rating folders inside each corresponding subfolder:

```text
Output/
├── AI/
├── Likely_AI/
├── Unsure/
└── Likely_Human/
```

If the input contains subfolders, those subfolders are recreated in the output directory.

## Important Limitations

This project uses heuristic scoring rather than an AI classification model.

- AI-generated media without recognizable metadata or filenames may be classified as human-made.
- Human-made media may receive high scores because of matching filenames, dimensions, or other properties.
- Common image resolutions and video frame rates are not proof of AI generation.
- Metadata may be missing, removed, or modified.
- Existing files in the output directory may be overwritten.

**Recommended:** Keep the output folder separate from the input folder. The script copies files, so the originals remain untouched.

## License

This project is licensed under the MIT License.
