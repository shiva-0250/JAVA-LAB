# EXPERIMENT-10
## 10.A. Without writing any code, build a GUI that display text in label and imagein an Image View (use JavaFX).
## Source Code:
``` java
<?xml version="1.0" encoding="UTF-8"?>

<?import javafx.geometry.Insets?>
<?import javafx.scene.control.Label?>
<?import javafx.scene.image.Image?>
<?import javafx.scene.image.ImageView?>
<?import javafx.scene.layout.VBox?>
<?import javafx.scene.text.Font?>

<VBox alignment="CENTER" spacing="10" xmlns:fx="http://javafx.com/fxml">
    
    <padding>
        <Insets top="10" right="10" bottom="10" left="10"/>
    </padding>

    <!-- Label to display text -->
    <Label text="Welcome to JavaFX" wrapText="true">
        <font>
            <Font size="20"/>
        </font>
    </Label>

    <!-- ImageView to display image -->
    <ImageView fitWidth="400" fitHeight="300" preserveRatio="true" smooth="true">
        <image>
            <Image url="@images/sample.jpg"/>
        </image>
    </ImageView>

</VBox>
```
## Steps:
```
Step 1: Create a new FXML document or open your GUI editor and choose a root
layout.
Choose a VBox (vertical box) to stack the text label above the image.
Step 2: Set properties on the VBox container.

Set spacing between children (for example 10 px), padding around the edges (for ex-
ample 10 px), and alignment to CENTER so children are centered horizontally.

Step 3: Add a Label as the first child of the VBox.
Enter the text you want displayed (for example: “Welcome to JavaFX”) and enable text
wrapping if needed.
Step 4: Configure the Label’s visual properties.
Set font size and weight (e.g., larger, bold font), alignment to center, and an optional
style class or inline style for color and spacing.
Step 5: Add an ImageView as the second child of the VBox.
Select the ImageView component from the library and drop it below the Label.
Step 6: Assign an image resource to the ImageView.

Choose an image file stored in your project resources (recommended folder: re-
sources/images/). Use a relative path so the FXML remains portable.

Step 7: Set sizing and scaling behavior for the ImageView.
Specify fitWidth and/or fitHeight (for example 400 × 300), enable preserveRatio = true
to maintain aspect ratio, and enable smooth = true for better scaling quality.
Step 8: Optionally set VBox.vgrow or other layout constraints.
If you want the image to expand when the window grows, set the ImageView’s vertical
grow to ALWAYS; otherwise leave default to keep fixed-size behavior.
Step 9: (Optional) Add fx:id values for the Label and ImageView.
If future code interaction is possible, assign fx:id="myLabel" and
fx:id="myImageView"; otherwise skip this step.
Step 10: (Optional) Link a stylesheet for consistent styling.
Add a CSS file to the project, reference it in the FXML document, and assign style
classes (for example .title-label) to the Label.
Step 11: Preview the layout in Scene Builder or the FXML editor.
Check that the text is readable, the image displays correctly, and resizing behaves as
expected.
Step 12: Save the FXML file and image resource in the project’s resources folder.
Confirm that the image path used by the ImageView is correct relative to the FXML
file.
Step 13: Document resource locations and any styling choices.
Write a short README note indicating where the image and FXML are saved and what
CSS (if any) is used.
Step 14: Hand off the FXML and resources for integration into a JavaFX application.
If someone later needs to load the UI from Java, they can use FXMLLoader to load the
saved FXML file.
```
## output:
![output of 10 A](10a.png)
