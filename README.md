# PROJECT TITLE: QR Code Generator
#### Video Demo:  < https://youtu.be/0gp2dTx0CJs?si=a3Jtlq2-Oj4qlXgg >
#### Description:
Briefly this project creates Qr codes by taking inputs from them. After generating Qr codes they can download or share the result. I used html, css and JavaScript language for this project.


- **CSS description**

This CSS code is for styling a web page that likely includes features for generating and sharing QR codes. Let's break it down:

- **Global Styling**: The `box-sizing` property ensures that padding and border are included in the element's total width and height. The `body` styling sets the background color to a dark shade of blue-black, uses a sans-serif font for text, centers content horizontally within a maximum width of 500 pixels, and vertically aligns content in the center of the viewport.

- **Input Styling**: Input fields of type color have no borders, a specific width and height, and slight border-radius for rounded corners.

- **Link Styling**: Anchor tags (links) have no text decoration.

- **QR Text Input Styling**: Text input for entering text related to the QR code generation is styled with padding, a background color, border, and placeholder text color.

- **QR Code Display Styling**: The container for displaying the QR code has fixed height and width, a border, and centers its content both vertically and horizontally.

- **QR Code Image Styling**: Any images or canvases within the QR code container have a maximum width and height of 100% to ensure they fit within the container without distortion.

- **Row Styling**: Elements with the class "row" are flex containers that evenly space their child elements horizontally.

- **Sizes Styling**: Elements with the class "sizes" have specific width, height, background, border, and text color.

- **Button Styling**: Buttons have text color, padding, background color, border-radius, and no border. They are flex containers that center their content both horizontally and vertically and change cursor on hover.

- **Button Icon Styling**: Any images within buttons have a specific width and left margin.

- **Share Button Styling**: Share buttons have a left margin.

- **Action Container Styling**: Flex container for arranging action-related elements with margin space around them.

- **Media Queries**: Adjustments for smaller screens are made using media queries. For screens below 512 pixels wide, the body width becomes 100%, padding is added to the body, QR code container size adjusts, and button minimum width is unset. For screens below 350 pixels wide, the action container changes its direction to column, and the share button's left margin and top margin are adjusted.



- **Javascript description**

This JavaScript code appears to be responsible for generating and handling a QR code dynamically based on user input. Let's break down the details:

1. **DOM Elements Selection**:
   - The code selects various DOM elements using `document.querySelector()` method and assigns them to variables. These elements include:
     - `.download`
     - `.dark`
     - `.light`
     - `#qr-code`
     - `.qr-text`
     - `.share-btn`
     - `.sizes`

2. **Event Listeners**:
   - Event listeners are attached to several elements to listen for specific events, such as `input`, `change`, and `click`. When these events occur, corresponding functions are executed.
   - For example, `handleDarkColor`, `handleLightColor`, `handleQRText`, `handleSize`, and `handleShare` functions are called when the respective events occur.

3. **Variables Initialization**:
   - `colorLight` and `colorDark` are initialized with default colors (`#fff` and `#000` respectively).
   - `size` is initialized with the default size of the QR code (300).

4. **Event Handler Functions**:
   - Functions like `handleDarkColor`, `handleLightColor`, `handleQRText`, `handleSize`, and `handleShare` are responsible for updating relevant variables and regenerating the QR code when user input or interaction occurs.

5. **generateQRCode Function**:
   - This function is called to generate the QR code.
   - It clears the content of the `qrContainer`, creates a new QR code using the `QRCode` constructor, and sets attributes such as `text`, `height`, `width`, `colorLight`, and `colorDark`.
   - It also updates the `href` attribute of the `.download` element with the data URL of the generated QR code image.

6. **handleShare Function**:
   - This function handles sharing of the generated QR code image.
   - It asynchronously fetches the QR code image as a blob, creates a File object, and then invokes the `navigator.share()` method to share the file.
   - It sets a timeout to ensure the share action is executed asynchronously.

7. **resolveDataUrl Function**:
   - This function returns a promise that resolves to the data URL of the QR code image.
   - It checks if the image is already loaded and returns its source, otherwise, it converts the canvas content to a data URL and resolves it.


- **HTML description**

This HTML code sets up a webpage for generating and interacting with QR codes. Let's break it down:

- **Document Type Declaration**: Specifies the HTML version and language.

- **Head Section**: Contains metadata like character encoding, viewport settings for responsive design, a link to an external stylesheet (`style.css`), and a title for the webpage.

- **Body Section**: Contains the main content of the webpage.

    - **Section Element**: Wraps the content of the webpage.

    - **Row Container**: Contains input elements and a select dropdown for customizing QR code appearance.
    
        - **Color Inputs**: Two color inputs for selecting light and dark colors for the QR code.
        
        - **Size Select**: A select dropdown for choosing the size of the QR code.
        
    - **QR Text Input**: An input field for entering the text to be encoded into the QR code.
    
    - **QR Code Display Area**: A div with the id "qr-code" where the generated QR code will be displayed.
    
    - **Action Container**: Contains buttons for downloading and sharing the QR code.
    
        - **Download Button**: An anchor tag styled as a button for downloading the QR code. It includes an image icon for download.
        
        - **Share Button**: A button for sharing the QR code. It includes an image icon for sharing.
        
- **Script Tags**: Includes links to external JavaScript libraries (`qrcode.min.js`) for generating QR codes and a custom JavaScript file (`scripts.js`) for handling interactions.

Overall, this HTML structure provides a user-friendly interface for generating and interacting with QR codes, allowing users to customize the QR code appearance and easily download or share it.