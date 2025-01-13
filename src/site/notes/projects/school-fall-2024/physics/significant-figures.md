---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/physics/significant-figures/"}
---


# Significant figures

- ***Significant Figures*** - The number of digits you can read from an instrument (including ***exactly one*** estimated digit).
    - On a digital instrument, the last digit you can see is always estimated
    - On an analog instrument, it is up to you to estimate the final digit by interpreting the position of the marker on the graduated scale.
- interesting fact: The meniscus in liquid measurements is a result of surface tension competing with adhesion of the liquid to the container.
    - If the liquid wants to stick to the container, the meniscus will look like a 'u'
    - If the liquid is repelled by the container, it will be humped upward like a droplet of water
- Accuracy vs. Precision
    - Accuracy indicates how close a measurement is to the true value
    - Precision indicates how close measurements are to each other (or how consistent the measurements are).
- Significant figures ensure that the precision of our computed answers matches the precision of our measurements
- They tell us how to combine different measurements with math, and come up with a reasonable answer.
- On the subject of hobbits (or zeroes)
    1. Leading zeroes are ***never*** significant
    2. Zeroes sandwiched between non-zero digits are ***always*** significant
    3. Zeroes at the end ***are significant***, but ***only if the number has a decimal point***
    4. Zeroes at the end are **ambiguous** if there is no decimal point
- Adding and subtracting numbers while respecting sigfigs
    - The answer has the same number of digits after the decimal point as the least-precise input
    - The least-precise input is the one with fewer digits after the decimal point.
- Multiplying and Dividing
    - The answer has the same number of sig figs as the least-precise input
    - The least-precise input is the one with fewer significant figures
- After you add, subtract, multiply, or divide, you use the extra digits beyond the sig figs to round the last sig fig.
