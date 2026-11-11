---
title: 'Technogym Skillbike update: Garmin watch now works'
tags: bicycles

---

Back in 2022, I wrote about [my struggles with the Technogym Skillbike smart
trainer][original-post]. Only Zwift and Rouvy worked with it, neither of which
runs well on a small screen. My Garmin Fenix 7S watch couldn't connect to it
either. Now, a few years later, I have some updates.

(I also [updated the original post][original-post-update].)

[original-post]: {% link _posts/2022-08-29-technogym-skillbike.md %}
[original-post-update]: {% link _posts/2022-08-29-technogym-skillbike.md %}#appendix-b-update-2026-11-11-garmin-works

After a long break from using the Skillbike, I finally tried connecting it to
my Garmin watch again.[^qz] This time, it worked! I was able to pair the
Skillbike with my Garmin Fenix 7S, and it stayed connected for the entire
ride. The watch controlled the Skillbike's resistance and recorded all the
relevant data, including power, cadence, and heart rate. The data synced
seamlessly to Garmin Connect, and I was able to see my training metrics and
suggested workouts on my watch as expected.

It's not smooth sailing yet, though. The Skillbike's and/or Garmin's (lol)
ANT+ implementation is still a bit finicky:

* The Skillbike's ANT+ ID changes every time it's powered on, so I have to
  re-pair it with my watch each time. This is annoying, but Garmin usually
  detects the Skillbike quickly, and pairing takes just a few seconds.

* It's necessary to pair the Skillbike with the watch before starting a
  workout. Otherwise, the watch won't set the initial resistance correctly,
  and the workout will be off. It's a nuisance, but it works fine as long as I
  remember to pair them in the right order.

Getting a meaningful structured workout onto the watch isn't straightforward,
either. Garmin Connect doesn't include a cycling workout library. Fortunately,
<https://intervals.icu/> integrates with Garmin Connect, letting you create
and upload structured workouts. It also offers plenty of pre-made workouts
from the community. As we've come to expect, there are quirks here, too:

* It's not possible to [configure a "power range" for indoor
  workouts][intervals-power-range]. As a result, the watch screams and
  vibrates whenever my power doesn't match the target exactly—which,
  realistically, it never does. This is super annoying, and the only
  workaround is to clear the "Indoor" checkbox manually for every planned
  workout, which is tedious and error-prone.

Finally, the watch shows only the current step, not an overview of the entire
workout.

I'd prefer to use a simple app like <https://auuki.com/> on my phone to
control the Skillbike, but last time I checked, it couldn't control the
Skillbike's resistance. It should be easy to look at how [qdomyos-zwift][]
does it, and open a pull request to Auuki. If only I enjoyed indoor cycling
enough to actually do that. <emoji>😆</emoji>

(This post was on the back burner for a long while, but I finally got around
to posting it after seeing [DC Rainmaker's post about cycling trainer
apps][dcrainmaker-app-roundup]. Apparently, there are many other apps one can
try. If only there was a reasonable chance that they would work with the
Skillbike…)

[intervals-power-range]: https://forum.intervals.icu/t/indoor-power-range-for-planned-garmin-activities/24976
[dcrainmaker-app-roundup]: https://www.dcrainmaker.com/2026/11/trainer-apps-roundup-coming-which-apps-to-include.html

[^qz]:
    This was inspired by an email from someone who got the Skillbike working
    via [qdomyos-zwift][]. I tried the app on my Android phone and eventually
    got it working, although it took a little more effort than expected: I had
    to build a snapshot of the app from source with [a little
    patch][qdomyos-zwift-patch] to make it recognise our Skillbike. The setup
    was quite complicated though, as QZ works as a bridge between the
    Skillbike and another device/app. This normally requires a second phone,
    although some apps (like Zwift) can connect on the same phone. It could
    maybe execute a structured workout itself, but the user interface is a bit
    too weird. I exchanged a few emails with the author, but ultimately gave
    up.

    And then I tried getting the Skillbike working with Garmin instead, just out of curiosity…

---

[qdomyos-zwift]: https://github.com/cagnulein/qdomyos-zwift
[qdomyos-zwift-patch]: https://github.com/cagnulein/qdomyos-zwift/commit/963a3fbb97d49e437b16924cc29231d838655993
