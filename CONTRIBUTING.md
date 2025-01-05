![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen?style=flat-square)

## Contribution Guidelines

Thank you for your interest in contributing to the icon repository! To ensure smooth collaboration, please follow these guidelines. Your contributions help make this project better.

## Table of Contents

- [Contribution Guidelines](#contribution-guidelines)
- [Table of Contents](#table-of-contents)
- [Icon Specifications](#icon-specifications)
  - [Format](#format)
  - [Cropping](#cropping)
  - [Light and Dark Versions](#light-and-dark-versions)
  - [File Naming](#file-naming)
  - [Quality Requirements](#quality-requirements)
- [Git Commit Messages](#git-commit-messages)
- [Contribution Process](#contribution-process)
- [Code of Conduct](#code-of-conduct)
- [Contact](#contact)

## Icon Specifications

### Format

- **SVG Format Required**: All icons should be submitted in SVG format. If an SVG version is unavailable, a PNG version will suffice, and a WEBP version will be accordingly.
- **Automatic PNG and WEBP Generation**: PNG and WEBP versions are generated automatically from the SVG (or PNG) files using the following settings:
  - **Dimensions**:
    - Height: 512 pixels
    - Width: Auto (maintaining aspect ratio)
  - **Transparency**: Enabled

### Cropping

- **Remove Empty Space**: Crop any empty space from your SVG files to ensure the icon is properly centered and sized. You can use [SVG Crop](https://svgcrop.com/) to assist with this.

### Light and Dark Versions

- **Monochrome or Single Primary Color Icons**:
  - If your icon is monochrome, please provide additional versions if applicable:
    - **`-light` Version**: For icons primarily dark or using black as a main color, provide a `-light` version for light backgrounds.
    - **`-dark` Version**: For icons primarily light or using white as a main color, provide a `-dark` version for dark backgrounds.
  - **Examples**:
    - A black logo should include a `-light` version where black is inverted.
    - A multicolored logo using black should provide a `-light` version with the black replaced.
  - **Tool Recommendation**: [DEEditor](https://deeditor.com/) can help adjust icon colors if needed.

### File Naming

- **Kebab Case**: Name your files using kebab case (lowercase words separated by hyphens). For example, "Nextcloud Calendar" becomes `nextcloud-calendar.svg`.
  - **Note**: Filenames are automatically converted to kebab case, but please double-check your naming to avoid conflicts or errors.

### Quality Requirements

- **No Upscaled Images**: Icons should maintain their original quality without artificial enlargement.
- **No Embedded Raster Images in SVGs**: Ensure that SVG files are true vector graphics without embedded raster images.

## SVG Cleaning Tips

The SVG format is complex in nature, as such, tricky issues can occur from time to time. 
Online tools mentioned here can assist to clean SVG files, but sometimes other tools such as text editors or Adobe Illustrator, can help the process.

### Issue: Image rendering with whitespace on top and/or sides in browsers (e.g. GitHub Commits or Browser Viewports)
![image](https://github.com/user-attachments/assets/351c713e-6b0e-48f9-a38d-9be1ba5ff13c)
![image](https://github.com/user-attachments/assets/5d1480f4-649d-4914-aa57-857e4f9bd02f)

This issue is (normally) caused by the SVG File **not** having width and height parameters specified. 
When these parameters are missing, the browser tries to interperate the **ViewBox** cleverly, but, unpredictability.

To fix this, add **width** and **height** parameters to match the **ViewBox**:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<svg id="Layer_1" xmlns="http://www.w3.org/2000/svg" width="85" height="85" viewBox="0 0 85 85">
	<path d="M18.6,0v18.6h47.8v47.8h18.6V26.6L58.5,0H18.6Z" style="fill:#de3c07;"/>
	<path d="M66.4,85v-18.6H18.6V18.6H0v39.9l26.6,26.5h39.8Z" style="fill:#de3c07;"/>
</svg>
```

If this issue persists, use a tool like Adobe Illustrator to check for unnecessary or incorrectly configured SVG elements.
![image](https://github.com/user-attachments/assets/00aaf67e-60e1-4459-b19f-b020c9c5e45d)

In this example, these items serve no purpose, and can be removed.

## Adobe Illustrator Notes
### Properly Aligning the Artboard
![image](https://github.com/user-attachments/assets/5fa497cb-c7e8-438f-a614-9a33014cba34)
In this example, we can see the Artboard is anchored to an arbitary location on the canvas. 

Ideally, it should be **top left anchored** to **0, 0**, like so:
![image](https://github.com/user-attachments/assets/473a3a94-091c-41f4-8fc8-cf8aec3c0325)
To move all items, **CTRL-A**, select the **Top Left Anchor** and enter **0, 0**


### Ideal Export Settings
![image](https://github.com/user-attachments/assets/aa12a528-b97a-488b-9907-81cc237e5573)

![image](https://github.com/user-attachments/assets/7b3ff6cd-da4c-4b79-9fbc-b200c6c189db)

**Most Importantly: Enable Minify, and Disable Responsive**
 - Inline Style, is generally, to help keep things tidy.
 - When _enabled_, **Minify**, as the name implies, minifies the output file.
 - When _disabled_, **Responsive**, adds **width and height parameters**.


## Git Commit Messages

- **Use Semantic Commits**: Follow the format <type>(scope): description:
  - `feat(icons): add nextcloud-calendar` when adding new icons.

## Contribution Process

1. **Fork the Repository**: Create a fork of this repository on your GitHub account.
2. **Clone the Repository**: Clone your forked repository to your local machine.
3. **Add Your Icons**: Place your SVG icon(s) into the appropriate directory, following the specifications above.
4. **Commit Your Changes**: Commit your additions with clear and descriptive commit messages using Gitmoji.
5. **Push to Your Fork**: Push your committed changes to your forked repository on GitHub.
6. **Create a Pull Request**: Submit a pull request to the main repository for review.

## Code of Conduct

By contributing, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Please review it to understand the expectations for all participants.

## Contact

If you have any questions or need assistance, feel free to reach out at [homarr-labs@proton.me](mailto:homarr-labs@proton.me). I'm happy to help.
