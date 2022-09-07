# Automated Testing Tools

## axe DevTools Browser Extension for Mozilla Firefox and Google Chrome

Lightweight and helps devs and testers assess content in the browser. Some of the key features include:

- Providing a comprehensive list of issues to fix in a single, detailed report
- Supporting color contrast analysis
- Interactive issue remediation
- Issue retesting

https://www.deque.com/axe/browser-extensions/

### How to use axe DevTools

1. First, download the axe DevTools extension for Firefox or Chrome 
2. Next, navigate to the web page you would like to test.
3. To access the extension, launch the developer tools menu within the browser. You can right-click on the web page and select Inspect from the menu. The keystroke Ctrl + Shift + I also opens developer tools in both browsers on Windows, and the keystroke Command + Alt + I opens developer tools in both browsers on macOS.
4. In the developer tools menu, locate the tab for the axe DevTools extension and open the tool.
5. Select the Scan All of My Page button in the tool to run an accessibility analysis of the web page. Once the analysis is done, results will appear within the tool.

### Understanding the axe DevTools report

Two panels appear:
- The left panel contains a list of accessibility issues found on the page, and the number of occurences. When one is selected,
- The right panel shows detailed information about that issue.

The detailed information includes:
- A description of the issue and a link to more info about it.
- Information about the impact of that issue.
- A button "inspect" that takes you directly to the code that triggered the issue.
- A button "highlight" that shows you where the issue occurs on the page (if it is visible)
- An out-of-context snippet showing the code that caused the issue.
- A list of guidelines to fix the issue.

## Firefox tools

- [Web Developer Toolbar for Mozilla Firefox](https://addons.mozilla.org/en-US/firefox/addon/web-developer/)
- The dev tools are listed here because they allow you to see code and the DOM.
- NoCoffee Vision Simulator (Last updated in 2017) allows you to simulate various low-vision conditions. https://addons.mozilla.org/en-US/firefox/addon/nocoffee/

## The rest

Most of the tools listed on this page are not worth mentioning because they are built into browsers now. The ones that are worht mentioning:

- Xcode has a tool called Accessibility Inspector which allows devs to analyze a page for accessibility especially as it relates to VoiceOver.
- You can get a tool called Accessibility Viewer (or aViewer) on Windows. Open source tool that allows you to access the accesibility API infor generated by browsers and screen readers.
