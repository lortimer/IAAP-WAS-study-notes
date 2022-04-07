# WCAG Guidelines Benefitting Cognitive Disabilities

WCAG only addresses cognitive disabilities in a few places. This is a gap in the guidelines

Some of the guidelines are generally good for all users, including people with cognitive disabilities.

Some users with reading disabilities use screen readers. Most users with cognitive disabilities do not.

## WCAG A-level guidelines

### 2.5.2 Pointer Cancellation: For functionality that can be operated using a single pointer, at least one of the following is true (Level A):

- No Down-Event: The down-event of the pointer is not used to execute any part of the function;
- Abort or Undo: Completion of the function is on the up-event, and a mechanism is available to abort the function before completion or to undo the function after completion;
- Up Reversal: The up-event reverses any outcome of the preceding down-event;
- Essential: Completing the function on the down-event is essential.

How this pertains to cognitive disabilities: All users benefit from an abort or undo feature that makes fixing mistakes easier. Users with cognitive disabilities might especially benefit from this feature.

### 3.3.1 Error Identification: If an input error is automatically detected, the item that is in error is identified and the error is described to the user in text. (Level A)

How this pertains to cognitive disabilities: Everybody needs to know when an error occurs, what the error is, and how to fix it. People with cognitive disabilities, especially, may have a hard time figuring out what the problem is if they don't receive guidance.

### 3.3.2 Labels or Instructions: Labels or instructions are provided when content requires user input. (Level A)

How this pertains to cognitive disabilities: Labels and instructions are good for everyone but can be particularly important for people with cognitive disabilities. The instructions for users with cognitive disabilities may have to be more explicit, clearer, and written in simpler language. It may even be best to put the instructions in a video or audio format.

## WCAG AA-level guidelines

### 1.3.5 Identify Input Purpose: The purpose of each input field collecting information about the user can be programmatically determined when: (Level AA)

- The input field serves a purpose identified in the Input Purposes for User Interface Components opens in a new window section; and
- The content is implemented using technologies with support for identifying the expected meaning for form input data.

How this pertains to cognitive disabilities: Users with cognitive disabilities might have difficulty with filling out forms. They may also prefer to use custom icon sets to label forms rather than words. Having a form that can be automatically filled out can be very helpful.

### 1.4.12 Text Spacing: In content implemented using markup languages that support the following text style properties, no loss of content or functionality occurs by setting all of the following and by changing no other style property: (Level AA)

- Line height (line spacing) to at least 1.5 times the font size;
- Spacing following paragraphs to at least 2 times the font size;
- Letter spacing (tracking) to at least 0.12 times the font size;
- Word spacing to at least 0.16 times the font size.

How this pertains to cognitive disabilities: Users with dyslexia might find it easier to read with extra spacing, and they may also use custom fonts to enhance readability.

### 1.4.13 Content on Hover or Focus: Where receiving and then removing pointer hover or keyboard focus triggers additional content to become visible and then hidden, the following are true: (Level AA)

- Dismissible: A mechanism is available to dismiss the additional content without moving pointer hover or keyboard focus, unless the additional content communicates an input error or does not obscure or replace other content;
- Hoverable: If pointer hover can trigger the additional content, then the pointer can be moved over the additional content without the additional content disappearing;
- Persistent: The additional content remains visible until the hover or focus trigger is removed, the user dismisses it, or its information is no longer valid

How this pertains to cognitive disabilities: All users need time to perceive, read, and process new content. Users with cognitive disabilities might find it particularly frustrating if content appears briefly and then disappears before they have a chance to review it.

### 3.2.3 Consistent Navigation: Navigational mechanisms that are repeated on multiple Web pages within a set of Web pages occur in the same relative order each time they are repeated, unless a change is initiated by the user. (Level AA)

How this pertains to cognitive disabilities: It can be disorienting when the interface—especially the main navigation—changes between views or pages. Some people with cognitive disabilities have a low tolerance for change and will find it difficult to learn new interfaces.

**Do not remove the current page from the navigation links. If you want, you can make it non-linked text**

### 3.2.4 Consistent Identification: Components that have the same functionality within a set of Web pages are identified consistently. (Level AA)

How this pertains to cognitive disabilities: Some people with cognitive disabilities will not be able to recognize that two names may refer to the same thing. For example, if there are two links, "Contact us" and "Call us," that point to the same web page, it is not immediately apparent that they would or should point to the same page. Another example: If there is a 5-step process, with each step requiring the user to click on a link to the go the next page, the word in the link should be consistent. It could say "Next" or "Continue" or some other word could be used, but it should always be the same word. Don't mix and match words.

### 3.3.3 Error Suggestion: If an input error is automatically detected and suggestions for correction are known, then the suggestions are provided to the user, unless it would jeopardize the security or purpose of the content. (Level AA)

How this pertains to cognitive disabilities: Some people with cognitive disabilities can become confused, disoriented, or discouraged if there is an error but they don't know why or how to fix it.

### 3.3.4 Error Prevention (Legal, Financial, Data): For Web pages that cause legal commitments or financial transactions for the user to occur, that modify or delete user-controllable data in data storage systems, or that submit user test responses, at least one of the following is true: (Level AA) 1) Reversible: Submissions are reversible. 2) Checked: Data entered by the user is checked for input errors and the user is provided an opportunity to correct them. 3) Confirmed: A mechanism is available for reviewing, confirming, and correcting information before finalizing the submission.

How this pertains to cognitive disabilities: People with cognitive disabilities are among the most likely to make mistakes. It is best to help them avoid mistakes before they become permanent.

## WCAG AAA-level guidelines 

### 1.3.6 Identify Purpose: In content implemented using markup languages, the purpose of User Interface Components, icons, and regions can be programmatically determined. (Level AAA)

How this pertains to cognitive disabilities: This success criterion is designed to help users customize their web experience. Users who find it easier to understand sets of icons than words would be able to place custom sets of icons on the screen through assistive technology. They could also hide extraneous regions of the page to help them focus on the content they want to see. This would be helpful to users who experience difficulty with reading, processing, or maintaining focus.

**Use the right ARIA landmarks and roles**

### 2.2.6 Timeouts: Users are warned of the duration of any user inactivity that could cause data loss, unless the data is preserved for more than 20 hours when the user does not take any actions. (Level AAA)

How this pertains to cognitive disabilities: Users with cognitive disabilities might take extra time to complete tasks. Ensuring that users are warned before a timeout can allow them to save their work or extend their session, so they don’t have to start from scratch.

### 3.1.3 Unusual Words A mechanism is available for identifying specific definitions of words or phrases used in an unusual or restricted way, including idioms and jargon. (Level AAA)

How this pertains to cognitive disabilities: Reading abilities vary. Some people cannot read at all. Others can read only at lower education levels.

Options for defining a word:
- Inline in a parenthetical
- In a tooltip
- In a definition list `<dl>` element. Link to the list from the word.
- In a `<dfn>` element
- Have the narrator define a word in the script for a multimedia project
- Show the definition of a word on the screen in an accessible format for a multimedia project

Inline and tooltips are good because the user doesn't have to leave the page or location on the page.

### 3.1.4 Abbreviations: A mechanism for identifying the expanded form or meaning of abbreviations is available. (Level AAA)

How this pertains to cognitive disabilities: Some people with cognitive disabilities do not know the meaning of some acronyms (indeed, this is true of many people without cognitive disabilities too). Also, the concept of what an acronym is may be difficult for some people with cognitive disabilities to understand. 

Options for defining an abbreviation:
- Inline
- In a Tooltip
- With an `<abbr>` element. **This is only accessible for mouse hover, not keyboard focus.**

### 3.1.5 Reading Level: When text requires reading ability more advanced than the lower secondary education level after removal of proper names and titles, supplemental content, or a version that does not require reading ability more advanced than the lower secondary education level, is available. (Level AAA)

How this pertains to cognitive disabilities: The comprehension levels of people with cognitive disabilities varies widely, from highly sophisticated at one end of the spectrum to very little language comprehension at the other. For those who experience difficulty processing language or reading, it can help to use simple words and simple sentence construction.

Options:
- Write at lowest reading level possible
- Summaries of the text are very helpful!
- Provide a simplified version of the text
- Supplement text with images or animation

Use a [Readability Checker](https://www.readabilityformulas.com/free-readability-formula-tests.php) to score your writing

### 3.1.6 Pronunciation: A mechanism is available for identifying specific pronunciation of words where meaning of the words, in context, is ambiguous without knowing the pronunciation. (Level AAA)

How this pertains to cognitive disabilities: Sometimes a person will know a word when they hear it but will not know it in its written form. Having a pronunciation guide can help.

Consider technical pronunciation syntax vs "phonetic" E.G. "\prə-ˌnən(t)-sē-ˈā-shən also ÷-ˌnau̇n(t)-\" vs. "pro-nun-see-AY-shun"

### 3.2.5 Change on Request: Changes of context are initiated only by user request or a mechanism is available to turn off such changes. (Level AAA)

How this pertains to cognitive disabilities: Some people with cognitive disabilities become confused when the interface changes, especially when the users themselves don't request the changes.

### 3.3.5 Help: Context-sensitive help is available. (Level AAA)

How this pertains to cognitive disabilities: People with cognitive disabilities are among the most likely to need help.

Options:
- Provide a help link per page
- Provide a live chat link or phone number
- Inline help text
- Pop-up help text with a question mark or "i" icon

### 3.3.6 Error Prevention (All): For Web pages that require the user to submit information, at least one of the following is true:

1. Reversible: Submissions are reversible.
2. Checked: Data entered by the user is checked for input errors and the user is provided an opportunity to correct them.
3. Confirmed: A mechanism is available for reviewing, confirming, and correcting information before finalizing the submission.

This is identical to 3.3.4, but AAA because it is not limited to legal, financial, and "data" situations.