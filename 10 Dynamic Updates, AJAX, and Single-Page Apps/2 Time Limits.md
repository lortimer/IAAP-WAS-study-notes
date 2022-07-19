# 2 Time Limits

## Session Timeout

### If there is a session time limit, users MUST be warned before the session ends and MUST be given time to save their data and/or extend the session.

A 2-minute warning is generally considered enough time.

#### Good Example

https://dequeuniversity.com/assets/html/module-dynamic/timeout/good/index.html

### Incomplete data SHOULD be saved after a session timeout.

Users may have to step away or get distracted. Don't assume they want to abandon the information. 

### Users SHOULD be warned of the duration of any user inactivity that could cause data loss, unless the data is preserved for more than 20 hours when the user does not take any actions

This criterion does not apply to content that is timed regardless of inactivity. See below for timed content.

When information cannot be saved for security or other reasons, you have other options:

- Give the user at least 20 hours, regardless of inactivity, to complete the task or form.
- Inform the user of the inactivity time constraint at the beginning of the task so that they can choose to prepare their information ahead of time (so they don’t need to run and find more documents to complete their taxes, for example, risking an inactivity timeout), and make sure any breaks they take or pauses they use to check their work are not too long. 

## Timers with Fixed Deadlines

### Timers with fixed deadlines SHOULD provide users with a dynamic countdown feature, especially if the deadline is soon

Timers need to be in ARIA live regions, and the "timer" role is off by default, not polite.

### Countdown features SHOULD post ARIA live announcements at strategic intervals

You don't want to announce a change to a timer every second. Good intervals depend on the activity. In a 1-hour test, warnings at 30 minutes, 15, 5, 2, and 1 make sense. In a 2-minute game of Gartic Phone, it makes sense to announce 30 seconds remaining, and maybe others.

#### Good Example

In the example below, the ARIA live announcements happen every 10 seconds and at 5 seconds remaining. The box with the timer in it also gains a highlighted state for sighted users.

The span with the current time is not in a live region. There is a hidden, assertive live region at the bottom of the timer where text is added.

The page title is also updated with the time remaining every second.

Finally, when time expires, the purchase button disappears and focus is moved to an announcement that time has expired so focus is not lost completely if it was on the button before.

https://dequeuniversity.com/assets/html/module-dynamic/deadline/good/index.html

### Countdown features MUST NOT post ARIA live so frequently that they become overwhelming to screen reader users

There's no quantitative rule for this, but the user needs to be able to read the rest of the page.

### If the timing is critical, a dynamic countdown MAY be included in the page `<title>`

This will give users the idea that timing is important when they load the page. They can tell how long they have to do whatever they're supposed to do. If the deadline is not "soon", this is not necessary.

### If the timing is critical, the dynamic countdown timers and alerts SHOULD be included across all relevant pages on the site.

If the timer is relevant on other pages. The course mentions an auction site as an example, but ebay doesn't give you timers on all pages, only on each item. I think they mean a site where there is only one item up for auction at a time.

## Auto Refresh/Reload

### The page MUST NOT refresh or reload automatically

This is bad for literally everyone. I can't think of any examples of no-warning, completely automatic refresh. The course says "news websites" do this.

Note that when a page is refreshed with Javascript, keyboard focus and viewport will not return to the same place on the page. If `<meta http-equiv="refresh" content="5">` is used, keyboard focus returns to the same place just like the viewport (if the same content is there)

### A web page MAY notify the user when a refresh is recommended.

With a dialog for urgent need or an alert message of some kind if it isn't urgent.

#### Good Example

https://dequeuniversity.com/assets/html/module-dynamic/reload/good/index.html?version=1