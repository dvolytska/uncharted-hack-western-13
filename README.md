> **Hack Western 13 project** · Western University's hackathon, November 2026 · theme "Discover the unknown"
>
> Built by **Thomson Lam** and **Daryna Volytska**. Entered in the **Canada Life Future Me Challenge** and **Organizers' Choice: Most Adventurous**.
>
> - **Daryna:** product and UX design, and the Uncharted mobile app's interface (`uncharted-app/src`, `docs/design-rules`)
> - **Thomson:** the road engine and server, the prototype playground (`playground/`), and the docs
>
> This is a copy of the team repo, [Thomson-Lam/hw](https://github.com/Thomson-Lam/hw).

> Code by **Thomson Lam** and **Daryna Volytska**. Entered in the **Canada Life Future Me Challenge** and **Organizers' Choice: Most Adventurous**.# Uncharted

We wanted to a) experiment with a new way to interact with and use LLMs to power the user experience, b) arrive at a same goal but through different processes and see what would happen, c) maybe not watch reels while Clauding and enrich ourselves organically without forcing ourselves to do so.

1. you enter something you want to do.
2. you scroll and make decisions.
3. you see the result of your decisions. If you don't like it and want to see more, keep scrolling.
4. you explore other ways you could have gotten to the same goal and try different things.

Is the gist of Uncharted. We combined the 2 things every hacker did this weekend, prompting and doom scrolling, into one thing, and let our choices take us down the new roads we make.

Uncharted can be used for:

- exploring ideas
- finding things
- learning things
- training long-term financial planning

**Canada Life track**: Uncharted is also an app that simulate scenarios that teaches you to make good investment decisions through simulations, with scrolling free of charge (if you can't fight it, join it!) and the randomness of LLMs.

> WARNING: Our harness is designed to force Gemini to be **creative** for the ideation scenario; it never repeats and has to keep exploring, so it gets desperate to make a good idea the more you scroll. You may run into *fun* ideas if you keep scrolling, so scroll with caution.

<p align="center">
  <img src="docs/screenshots/IMG_6415.jpg" width="250" alt="Idea card: Dark Beat Singletrack, a rhythmic nighttime mountain bike descent. Your choices: 25." />
  <img src="docs/screenshots/IMG_6416.jpg" width="250" alt="Idea card: Data Trail Chart Stream, review digital charts for the trail ahead. Your choices: 47." />
  <img src="docs/screenshots/IMG_6417.jpg" width="250" alt="Idea card: Visual Fauna Log Feed, read animal data tracks in the dark. Your choices: 48." />
</p>

Once in a while, a nice surprise from Wikipedia pops out when exploring ideas.

## Scroll yourself 

1. Clone and install

 ```bash
git clone https://github.com/Thomson-Lam/hw.git
cd hw/uncharted-app
npm ci
 ```

2. Add your key to hw/.env, at the repo root, not inside uncharted-app/

 ```bash
echo 'GEMINI_API_KEY=your-key-here' > ../.env
```

The server reads this file at startup (server/server.mjs:10). If the file is missing,
it crashes, even when you set UNCHARTED_GEMINI_KEY instead. The repo has no .env.example.

3. Start the road server (port 8787)

```bash
node server/server.mjs
 ```

It creates uncharted.sqlite on the first run.

4. Start the app in a second terminal

```bash
npx expo start --lan
```

- Phone: scan the QR code with Expo Go. The phone and laptop must be on the same Wi-Fi, because the app calls <laptop-ip>:8787.
- Laptop: press w for the web build, or run ./sim.sh for a phone-sized Chrome window.

If you use Mac, hotspot and run `./phone.sh`. It finds the hotspot address and restarts Expo on it.

Optional: the playground (prototypes, Next.js)

```bash
cd ../playground && npm install && npm run dev
```

## some nice to have next steps?

Maybe random retro games and comics to go along with the nice HW components. No videos though; we want to keep our minds fresh and focused.

## Credits

- Mountain and sky art (`mountain-1…4.webp`, `sky-noise.webp`) comes from the [Hack Western website](https://github.com/hackwestern/hackwestern), MIT License, © 2025 Hack Western. The full notice is in [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md).
- `uncharted-app/` started from the Expo app template (MIT, © 650 Industries).
