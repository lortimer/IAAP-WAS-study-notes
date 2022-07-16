# Seizure-Inducing Flashes

Seizures are abnormal or erratic electrical impulses in the brain that can interfere with someone's ability to process information or cause involuntary muscle movment, putting the brain's owner at risk of injury.

Flashing lights can trigger seizures. Pokemon and a Twilight movie are two instances of media that have caused seizures in their viewers. In Pokemon's example, the flashing was a roughly 30hz strobe alternating between red and blue. It's freaky to see.

## A page MUST NOT contain content that flashes more than 3 times per second, unless that flashing content is sufficiently small, and the flashes are of low contrast and do not exceed general flash thresholds or red flash thresholds

Specific conditions that allow an image that flashes more than 3 times per second:
- The flashing area is "small enough"
  - This means "less than 25% of 10 degrees of visual field", which is not possible to measure for every given device. The heuristic to follow is that it should be no more than 21,824 square pixels of any shape.
- The contrast of the flashing content is "low enough."
  - There is a tool, linked below, to test this rule.

Generally, eliminate all flashes where possible.

### Some other technical information

- "general flashes" are pairs of opposing changes in relative luminance of 10% or more of the maximum relative luminance...
- "red flashes" are any pair of opposing transitions involving saturated red.

[There are formulae for this at w3.org](https://www.w3.org/TR/UNDERSTANDING-WCAG20/seizure-does-not-violate.html#general-thresholddef)

[The Photosensitive Epilepsy Analysis Tool (PEAT)](https://trace.umd.edu/peat/) allows you to test a video to see if it has too much flash

[Understanding the flash success criterion](https://www.w3.org/TR/WCAG20-TECHS/G176)