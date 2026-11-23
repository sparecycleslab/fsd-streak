# FSD Perfect Streak

A tiny calculator that answers an uncomfortable question: if you drive only on FSD from here on, how far would you have to go to raise your score?

Live page: [https://sparecycleslab.github.io/fsd-streak/](https://sparecycleslab.github.io/fsd-streak/)

Enter the distance you have already driven on FSD and your total distance. The page shows your current ratio, the perfect-FSD distance needed for a few milestones (the next whole percent, 95%, 99%, and 99.9%), and a curve that starts at your current score and climbs toward 99%. Units can be miles or kilometers; they only change the labels. The math is the same either way.

Links are shareable. The address bar updates as you type (`?f=14232&t=15270&u=mi`), and **Copy link to my numbers** copies that URL so someone else can open your exact result.

## The math

Let \(f\) be distance already driven on FSD and \(t\) be total distance driven. Your current ratio is

\[
r_0 = f / t
\]

To reach a higher target ratio \(r\) by driving only on FSD, the extra distance \(x\) is

\[
x(r) = \frac{t - f}{1 - r} - t = \frac{r t - f}{1 - r}
\]

A quick sanity check: if you are at 93.2%, getting to 94% takes about \(0.1333 \times t\) of perfect FSD. After that the curve gets steep in a hurry. 99.9% is, for most of us, a lifetime of flawless driving.

This is a simple ratio of two odometer numbers. Tesla’s in-car FSD stats may be computed differently. The page is not affiliated with Tesla, Inc.

## Publish on GitHub Pages

The site is a static `index.html` (plus `og.png` for link previews). There is no build step.

1. Create a public repository named `fsd-streak` under [github.com/sparecycleslab](https://github.com/sparecycleslab), with no README, license, or `.gitignore` (this folder already has those files).

   ```bash
   gh repo create sparecycleslab/fsd-streak --public --description "FSD perfect streak calculator"
   ```

   Or create it in the GitHub UI: **New repository** → name `fsd-streak` → Public → create, and do not add a README.

2. From this folder, add the remote and push the `main` branch:

   ```bash
   git remote add origin https://github.com/sparecycleslab/fsd-streak.git
   git push -u origin main
   ```

   SSH works the same way if you prefer: `git@github.com:sparecycleslab/fsd-streak.git`.

3. On GitHub, open the repo → **Settings** → **Pages**. Under **Build and deployment**, set:

   - Source: **Deploy from a branch**
   - Branch: **main**, folder: **/ (root)**
   - **Save**

   After a minute or two the site will be live at `https://sparecycleslab.github.io/fsd-streak/`.

## Author

Spare Cycles Lab ([sparecycleslab@gmail.com](mailto:sparecycleslab@gmail.com))

[https://x.com/sparecycleslab](https://x.com/sparecycleslab)

## License

This software is licensed under the MIT License. Copyright (c) 2026 Spare Cycles Lab. The full license text is in [LICENSE](LICENSE).

## Disclaimer

This project is not affiliated with, endorsed by, or sponsored by Tesla, Inc. The calculator is a simple ratio of two distances you enter. Real in-car FSD stats may be computed differently.
