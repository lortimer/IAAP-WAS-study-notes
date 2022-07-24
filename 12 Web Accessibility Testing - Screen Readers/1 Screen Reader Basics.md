# Screen Reader Basics

## What Are Screen Readers?

### Text to speech or braille

Screen readers are software programs that convert digital text into speech (via a software-based voice synthesizer) or braille output (to a refreshable braille device). Full-featured screen readers can read the interface and content in operating systems, software, web sites, and other digital assets.

Most users listen to the output as a synthesized voice. However, most major screen readers can output to refreshable braille devices in addition to the audio output or not.

Operating systems and browsers have an accessibility API to convey information about the names, roles, values, and structure of screen content plus events that should be announced.

## Who Uses Screen Readers?

The majority of users are blind, which includes people who cannot see at all, or who have some vision.

People with both visual and auditory disabilities may use a screen reader with a braille device.

People with low vision usually use screen magnification software to be able to see parts of the screen, and they may also use a screen reader.

People with reading disabilities or cognitive disabilities may find it easier to listen to web content instead of reading it.

People with and without disabilities can use screen readers in eyes-free or hands-free environments.

## Why Test with Screen Readers?

### End Users

Real people actually need to use screen readers as their only way to interact with the web. Their experience is just as important as everyone else's.

### Automated accessibility tools can't catch every accessibility issue

Automated tools can catch obvious issues like missing alt text or input labels. As the UI and accessibility violations get more complex, these tools become less effective. The standard estimate is that these tools can assess 30% to 50% of accessibility issues.

The cannot judge the **quality of subjective content** like alt text. It can't tell if it is accurate and meaningful.

Automated tools also can't reliably determine if **keyboard focus patterns** make sense for users. Did the focus move to the right element when a button was clicked? Do the tab stops on the page make sense?

**Custom Widgets** are very difficult for an automated tool to understand, let alone say is accessible.

### Custom widgets with JavaScript and ARIA require screen reader testing

### Screen reader brands aren't exactly alike

When testing static HTML accessibility, one screen reader (on each mobile and desktop) is usually enough, and it doesn't matter which.

When testing dynamic content like custom widgets and form validation, it's important to test with at least 2 screen readers because of the small differences in the way they work, which includes bugs

## Which Screen Readers Should You Test With?

[Screen Reader and browser combination rankings](https://webaim.org/projects/screenreadersurvey9/#browsercombos) from WebAIM's Survey in 2021:

| Screen Reader and Browser    | # of Respondents | % of Respondents |
|------------------------------|------------------|------------------|
| JAWS with Chrome	            | 500              | 	32.5%           |
| NVDA with Chrome	            | 246              | 	16.0%           |
| JAWS with Edge	              | 194              | 	12.6%           |
| NVDA with Firefox	           | 149              | 	9.7%            |
| JAWS with Firefox	           | 74               | 	4.8%            |
| VoiceOver with Safari	       | 72               | 	4.7%            |
| NVDA with Edge	              | 55               | 	3.6%            |
| ZoomText/Fusion with Chrome	 | 33               | 	2.1%            |
| JAWS with Internet Explorer	 | 30               | 	1.9%            |
| VoiceOver with Chrome	       | 24               | 	1.6%            |
| ZoomText/Fusion with Edge	   | 18               | 	1.2%            |
| Other combinations	          | 144              | 	9.4%            |

### Combination 1: Firefox and NVDA, or Chrome and NVDA, or Edge and NVDA

NVDA use has been growing for a long time, although started to dip in the last survey after briefly overtaking JAWS. NVDA provides a tool called the Speech Viewer which allows you to see the screen reader output to more easily identify errors.

Chrome and Edge are effectively the same now, so you cover more users with them.

### Combination 2: Chrome and JAWS, or Edge and JAWS

JAWS is the most popular screen reader and has been for a long time, except for a short time when NVDA beat it out by a small margin. JAWS was updated at one point to work specifically with Chrom (and therefore Edge also)

JAWS tries to guess when something is wrong, like a missing form label, and it often guesses correctly. The potential problem is that a tester may assume there is no problem because JAWS was able to guess correctly.

### Mobile

It is important to test with both VoiceOver with Safari (iOS), and TalkBack with Chrome (Android) because users widely own both products, and the two programs vary in scope and ability. Only about 6% of desktop screen-reader users use MacOS, but for mobile it's much closer to 75%, at least in the US. VoiceOver tends to have more capabilities than TalkBack, so it is important to make websites accessible for both mediums.

### Other browsers and screen readers

It is usually sufficient to test in either Firefox/NVDA or Chrome/JAWS. When there is tricky interactive content on the page, you're best off testing in 2 or 3 environments plus mobile.

The experience is best when screen readers are paired with their favorite browsers, although they may support others.

### Capturing screen reader output with NVDA

The NVDA speech viewer, when activated, shows lines of text spoken by the screen reader, which can be helpful for documenting issues.

<img src="https://dequeuniversity.com/assets/images/module-using-screen-readers/nvda-speech-viewer.png" alt="Screenshot of the windows operating system showing the NVDA Speech Viewer window with a series of the text spoken previously.">

## Can Websites Detect Screen Readers?

### NO, Web servers can't detect screen readers

Screen readers don't interact directly with web servers. They interact directly with the browser and do not send requests. There is no way to tell if the user is using a screen reader (except by collecting data on how they interact with your pages, analyzing it, and making an educated guess. And that would be very creepy and bad.)

### What if you could detect screen readers?

The temptation to detect whether a user is using a screen reader should be SQAUSHED. It would allow you to create a separate and unequal experience for screen reader users, which would likely mean creating a worse experience for screen reader users. It would be less well-maintained and easy to leave behind when there's only so much time for development. You could also strip out parts of the design that are important for everyone, but feel unimportant to people who aren't experienced at designing for screen reader users.

Even worse than designers are bean counters who may argue that we should neglect screen-reader users because they represent a low percentage of the market. This feeds itself, because if a site is inaccessible, people who use screen readers are unlikely to use it, making the source of that information unreliable.

Choosing not to support screen readers is a purposeful act of discrimination against people with disabilities. People cannot leave their disabilities behind, so accessibility is important for creating a built world that everyone can take advantage of.

Flash actually was able to tell if software was running that was getting accessible information from the Microsoft Active Accessibility API, which includes JAWS, Zoomtext, and Dragon Naturally Speaking. This feature was not able to detect all assitive technologies and was used to create poor-quality "accessible" versions of sites.

## Windows Screen Readers on a Mac

NVDA and JAWS both use the insert key as the main modifier key, and Mac keyboards don't usually have that key. So there are some options for using them on a Mac. The course is actually advocating to install a Windows virtual machine on the Mac first because these two screen readers don't work on MacOS.

### Option 1: Hardware

Use an external keyboard

### Option 2: Software - SharpKeys or Karabiner Elements

Remap an unused key to be the insert key.