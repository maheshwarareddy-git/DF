# Exp no :08 Date :

# Use Steg-Expose to Detect Hidden Data in Images

## Description

**StegExpose** is a specialized tool used for **steganography analysis**. It works by evaluating the **statistical properties** of an image to estimate the probability of hidden data being embedded within it. This process helps forensic investigators detect steganography techniques like Least Significant Bit (LSB) embedding.

## Prerequisites

- Java Runtime Environment (JRE): StegExpose is a Java-based application and requires JRE to run.
- StegExpose Tool: Download the latest .jar file from the official StegExpose GitHub repository.

## Step-by-Step Process

### 1. Download and Set Up StegExpose

1. Download the tool: Obtain the StegExpose.jar file from the GitHub repository.
2. Install Java: Ensure JRE is installed on your machine.
3. Prepare environment: Place the StegExpose.jar file in a dedicated working folder.

![Java Setup - Complete](images/page-01-screenshot-01.png)

### 2. Select Images for Analysis

- Collect the images you suspect might contain hidden data.
- StegExpose supports common image formats such as .png, .jpg, and .bmp.

![File Explorer showing myimages folder](images/page-02-screenshot-01.jpg)

### 3. Open Command Line or Terminal

- Navigate to the folder where the StegExpose.jar file is located using your Command Prompt (Windows) or Terminal (Linux/macOS).

![Windows PowerShell](images/page-02-screenshot-02.jpg)

### 4. Run StegExpose on an Image

- Use the following command structure to analyze a single image for hidden data:

**Command Structure:**

```bash
java -jar StegExpose.jar <image_file_path>
```

**Example:**

```bash
java -jar StegExpose.jar test_image.png
```

### 5. Analyze the Output

- StegExpose calculates a **"suspect" score** ranging from 0 to 1. **The higher the score, the more likely steganography is present.**

| Score Range | Interpretation (Suggested Thresholds) |
|---|---|
| **Less than 0.2** | Image is considered **clean** (no hidden data detected). |
| **0.2 - 0.3** | **Possibly** some hidden data is present. |
| **Above 0.3** | **Likely** that steganography is present. |

- **Example Output Analysis:**

```bash
java -jar StegExpose.jar suspect_image.png
```

```text
Analyzing suspect_image.png...
```

```text
Result: 0.4
```

```text
Steganography likely present
```

![Windows PowerShell](images/page-03-screenshot-01.jpg)

![Windows PowerShell](images/page-04-screenshot-01.jpg)

### 6. Batch Analysis (Multiple Images)

- To check multiple images at once, specify the folder path containing the images:

**Command Structure:**

```bash
java -jar StegExpose.jar <folder_path>
```

### 7. Advanced Options (Optional)

- To view additional parameters, such as options for adjusting detection sensitivity or output verbosity, use the --help flag:

**Command:**

```bash
java -jar StegExpose.jar --help
```

### 8. Review the Results

- Review the scores generated for each image and use the threshold values to determine which images require further forensic investigation to extract the suspected hidden data.

**Result:**

The hidden data within the image was successfully detected using StegExpose. The analysis revealed that images with a suspect score above the threshold likely contain embedded steganographic content, confirming the tool’s effectiveness in steganography detection.
