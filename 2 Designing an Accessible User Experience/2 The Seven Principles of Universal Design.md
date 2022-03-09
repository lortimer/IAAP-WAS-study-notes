# The 7 Principles of Universal Design

"[The Principles of Universal Design](https://www.ncsu.edu/ncsu/design/cud/pubs_p/docs/poster.pdf)" was developed and written by a group of architects at NC State in 1997. It lays out the principles for designing physical spaces to be inclusive with universal techniques.

## 1. Equitable Use

Goal: The design is useful and marketable to people with diverse abilities

Guidelines:

<ol type="a">
  <li>Provide the same means of use for all users: identical whenever possible; equivalent when not.</li>
  <li>Avoid segregating or stigmatizing any users.</li>
  <li>Make provisions for privacy, security, and safety equally available to all users.</li>
  <li>Make the design appealing to all users.</li>
</ol>

Good Examples:
 - Powered, automatic doors
 - A website with semantic markup to make itself accessible to sighted and blind users

Bad Examples:
 - A website with a version for sighted users and a version for blind users.
   - Two versions is not an equivalent experience
   - It is stigmatizing to use the "special" version
 - An inaccessible website with an "accessible" phone experience

## 2. Flexibility in Use

Goal: Provide options for use - the design accommodates a wide range of individual preferences and abilities.

Guidelines: 
<ol type="a">
  <li>Provide choice in methods of use.</li>
  <li>Accommodate right- or left-handed access and use.</li>
  <li>Facilitate the user's accuracy and precision.</li>
  <li>Provide adaptability to the user's pace.</li>
</ol>

Good Examples:
 - An automated teller machine (ATM) that has visual, tactile, and audible feedback, a tapered card opening, and a palm rest.
 - A JavaScript drag-and-drop widget is designed to work with any of the following: a mouse, a touchscreen, or a keyboard.
 - A bank web site warns the user 2 minutes before the session is about to expire and gives the user the option of extending the session. The warning itself is fully accessible to keyboard and screen reader users and is easy to respond to quickly.

Bad Examples:
 - A web form that requires the user to click a button to submit, but the button is not accessible via the keyboard.
 - A mobile web site has three superscripts after a word, each linked to a footnote at the bottom of the page. Each superscript is tiny, and all of them are very close to each other, making it almost impossible to activate the correct link accurately.

## 3. Simple and Intuitive Use

Goal: Use of the design is easy to understand, regardless of the user's experience, knowledge, language skills, or current concentration level.

Guidelines:
<ol type="a">
  <li>Eliminate unnecessary complexity.</li>
  <li>Be consistent with user expectations and intuition.</li>
  <li>Accommodate a wide range of literacy and language skills.</li>
  <li>Arrange information consistent with its importance.</li>
  <li>Provide effective prompting and feedback during and after task completion.</li>
</ol>

Good Examples:
- An instruction manual with images and no text
- Consistent design of escalators
- TLDRs
- A form validation script provides clear success confirmation messages when the form is submitted successfully, and clear error messages when there is a problem with the data. The focus moves to the error messages, ensuring that keyboard and screen reader users get the full benefit of the messages.
- Using heading tags correctly
- Consistency across the pages of a website

Bad Examples:
- An e-commerce site requires many detailed steps to complete a purchase, making the process unnecessarily complex.
- A web site uses custom JavaScript widgets that are new in design and concept, and unfamiliar to users.
- A form validation script highlights a field with an error but does not explain what the error is or how to fix it.

## 4. Perceptible Information

Goal: The design communicates necessary information effectively to the user, regardless of ambient conditions or the user's sensory abilities.

<font size="6">Your sensory abilities shouldn't prevent you from gathering the information you need</font>

Guidelines:
<ol type="a">
  <li>Use different modes (pictorial, verbal, tactile) for redundant presentation of essential information.</li>
  <li>Maximize "legibility" of essential information.</li>
  <li>Differentiate elements in ways that can be described (i.e. make it easy to give instructions or directions).</li>
  <li>Provide compatibility with a variety of techniques or devices used by people with sensory limitations.</li>
</ol>


Good Examples:
- Redundant cueing (e.g. voice communications and signage) in airports, train stations, and subway cars.
- ARIA live announcements are used to announce to screen reader users the number of available options in a custom ARIA/JavaScript autocomplete drop-down list (e.g. "There are three cities that start with 'SAN.' Use the down arrow key to navigate the options").

Bad Examples:
- A low contrast color scheme on a web site makes it difficult for people with low vision to read the text or distinguish buttons from the surrounding text.
- A video tutorial on how to tie your shoes is shown with no narration, making the video useless for a person who is blind.

## 5. Tolerance for Error

Goal: The design minimizes hazards and the adverse consequences of accidental or unintended actions.

Guidelines:
<ol type="a">
  <li>Arrange elements to minimize hazards and errors: most used elements, most accessible; hazardous elements eliminated, isolated, or shielded.</li>
  <li>Provide warnings of hazards and errors.</li>
  <li>Provide fail safe features.</li>
  <li>Discourage unconscious action in tasks that require vigilance.</li>
</ol>

Good Examples:
- A double-cut car key easily inserted into a recessed keyhole in either of two ways.
- An "undo" feature in computer software that allows the user to correct mistakes without penalty.
- On a financial web site, a script confirms "Are you sure you want to transfer funds?" before funds are transferred, in case users had pressed the button by accident, or before they were sure they wanted to do it.
- A search feature performs a spell check on submissions and suggests corrections.

Bad Examples:
- A web site responds to a "delete account" request without confirming with the user, resulting in the irreversible loss of the account.
- A search feature searches only for the literal string of text and doesn't take into account variations in word order, spelling, etc.

## 6. Low Physical Effort

Goal: The design can be used efficiently and comfortably and with a minimum of fatigue.

Guidelines:
<ol type="a">
  <li>Allow user to maintain a neutral body position.</li>
  <li>Use reasonable operating forces.</li>
  <li>Minimize repetitive actions.</li>
  <li>Minimize sustained physical effort.</li>
</ol>

Good Examples:
- Lever or loop handles on doors and faucets.
- Touch lamps operated without a switch.
- A web site has a "skip to main content" link at the top, allowing keyboard users to avoid tabbing through all of the links in the header and navigation.
- A web site has good heading and landmark structure (importantly, the content starts with an `<h1>` heading, inside a `<main>` landmark, among others), allowing screen reader users to navigate by headings and landmarks to the part of the page they're interested in.

Bad Examples:
- A sign-up process on a web site requires typing a large amount of information, which can lead to fatigue in people with motor disabilities.
- A web site is designed with many links in the header and navigation section, and no headings, landmarks, or "skip to main content" link to allow users to jump to the main content.

## 7. Size and Space for Approach and Use

Goal: Appropriate size and space is provided for approach, reach, manipulation, and use, regardless of user's body size, posture, or mobility.

Guidelines:
<ol type="a">
  <li>Provide a clear line of sight to important elements for any seated or standing user.</li>
  <li>Make reach to all components comfortable for any seated or standing user.</li>
  <li>Accommodate variations in hand and grip size.</li>
  <li>Provide adequate space for the use of assistive devices or personal assistance.</li>
</ol>

Good Examples:
- Controls on the front and clear floor space around appliances, mailboxes, dumpsters, and other elements.
- Wide gates at subway stations that accommodate all users.

The reading says this principle doesn't apply to the web as readily as the others because it has more to do with physical environments than anything else.

I disagree. I think the idea of putting UI elements "within reach" is quite relevant to mobile and touch-screen interfaces because people tend to hold their phones with one hand and use their thumbs to interact with the screen.

I also find many UIs quite cluttered, and I accidentally click on the wrong buttons because they're too close together. "Leaving space for use" means making buttons big and well-spaced.

I think the class would categorize those as falling under "flexibility in use", but I would argue they fit here.