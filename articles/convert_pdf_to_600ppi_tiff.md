# Convert PDF to 600ppi TIFF

Just like PhotoShop, Gimp can convert back and forth between different file format. This tutorial we'll demo how to convert a PDF file with two pages to be two different TIFF files with 600ppi.


## Installation

Gimp is a free software across all three major operating system: Windows, Mac, and Linux. In this tutorial we'll use Windows as example, but the same steps can be shared across Mac and Linux users. 

It can be downloaded here: https://www.gimp.org/downloads/. Simply download it for your specific OS, and use the installer to install. After installation, open the Gimp app. Notice that the first time open might take a few minutes, because it'll query the available plugins and install them. Also make sure you have internet connect in the first time open.

## Step-to-step Instructions

The following are the step to step instructions for the conversion steps:

### Import pdf file with 600ppi
We will use this [sample_pdf](../assets/sample_pdf.pdf) to illustrate the steps.
1. Open Gimp, `File -> Open` then navigate to the sample_pdf.pdf to open it.
2. A window will prompt with the import options, like the follow picture. Current *Resolution* is `100 pixel/inch`, *Width* is `850px`, *Height* is `1100px`.
3. Update the resolution to be 600 pixel/inch, notice that *Width* and *Height* will automatically change with the Resolution, to become `5100px` and `6600px`, leave these values for now. Also update the `Open page as` field to be from `Layers` to `Images`. Then click *Import* button.


### Scale Image
After import, the project will have two images opened in two tabs (corresponding to PDF page #1 and page #2). You may have more tabs open if you have more pages. The handling for each page/image is exactly the same:
1. Select a image (you do from switch tab), navigate `Image -> Scale Image`, after click you'll see the following option
2. Change the *Width* and *Height* to be smaller value, you can use the original pdf's dimension when import, in this case it should be `850px x 1100px`. The resolution is correct, so no need to change. Interpolation option is up to you (if there's special requirement), cubic and linear are commonly used options. Then click scale.

### Export as TIFF Image
After scale the image, we need to export it as TIFF iamge format.
1. Click `File -> Export As`, a "Export Image" window will open. The default name is from the original pdf file, which is `sample_pdf.pdf`, change it to any preferred name end with `.tiff`, for example `page1.tiff`
2. Then a "Export Image as TIFF" window will prompt, you might need to choose a Compression option if you want the image to be smaller. JPEG is the most popular one. Then click `export`
3. Save the result TIFF file to your desired location

### Repeat the Scale/Export steps
Repeat "Scale Image" and "Export as TIFF Image" for each of the pages in the PDF (corresponding to tabs in the Gimp). Then you're all set.
Here's the result from the [sample_pdf](../assets/sample_pdf.pdf): [page1.tiff](../assets/convert_pdf_to_600ppi_tiff/page1.tiff) and [page2.tiff](../assets/convert_pdf_to_600ppi_tiff/page1.tiff).