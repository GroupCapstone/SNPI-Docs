# 10 Niche Animation Hacks
Spoken text from the video, recorded 2026-11-25.

Intro: Here are 10 animation hacks that will make your app feel like Apple.

1. Scale from 0.97
Scale from 0.97.

2. Press feedback
Also, scale buttons down to 0.97 when they're pressed, so it feels more responsive.

3. Shake on error
If a password's wrong, don't just turn it red, shake it too so it's obvious.

4. Directional slides
Don't fade between steps in a stepper. Slide it in the appropriate direction instead.

5. Smooth height: auto
Accordions jump because height: auto can't be animated. Add interpolate-size so it opens smoothly.

6. Transform, not left
Animating top or left is slow because the browser repaints every frame. Animate transform instead to keep it smooth.

7. Instant theme switch
Switching themes can fire every transition at once, which can look glitchy. Turn off the transition during the switch.

8. Tooltip skip delay
Waiting for every tooltip can feel slow. Only delay the first one and make everyone after snappy.

9. Velocity springs
A fixed transition can make a flick feel mechanical. Use a spring to keep your speed.

10. Rubber banding
If you pull past the end of a carousel, add resistance, rubber band.

Closing line: Follow for more.
