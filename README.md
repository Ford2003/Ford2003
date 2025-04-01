# About Me

Hi, I'm Tommy, a 3rd year BSc Mathematics student, who is also a keen programmer hoping to join the realm of software engineering!

My primary language which I've been learning since I was 16 is **Python**. After completing multiple online [CodeCademy](https://codecademy.com) courses and various personal projects. I feel I have really thrived in the language, giving me solid and consistent programming style to go out and explore different languages and frameworks. Throughout this ReadME, I will share my programming journey.

**LinkedIn Profile -> [Here](https://www.linkedin.com/in/tommy-ford03/)**

## Skills

- **Python**
- **C++**
- **Javascript/Typescript**
- A hint of **React**, **Vite** and **Express**
- Some basic **assembly**
- Simple **CPUs** (6502) and their implementation in **electrical circuits**
- **Arduino**
- **Unreal Engine 5** blueprints mainly and some **C++**
- **Git** and **GitHub**
- **CI/CD** with **GitHub Actions**
- **Web server deployment** with **Linux Ubuntu**

## Projects

### [6502_EM](https://github.com/Ford2003/6502_EM)

This is a project I am particularly proud of. Inspired after watching Ben Eaters YouTube playlist on [building an 8-bit breadboard computer](https://www.youtube.com/playlist?list=PLowKtXNTBypGqImE405J2565dvjafglHU) I became particularly interested in the **6502 CPU** as this computer used a very similar, but simplified architecture and I learned a lot about how CPUs generally worked at a sort of mid-level perspective. This interestingly really helped me with understanding **optimisation** in my programming, in the sense of reducing the number the CPU operations or using faster operations. In order to really understand the CPU I decided to make this emulator. You can instantiate a memory module object, the cpu and the clock and directly input a binary program into the memory and when the CPU is ran it will accurately run the program you input, accurate to the point of using the correct number of clock cycles at each stage of each operation. The main challenge of this project was **concurrency**, I needed to find a way for the clock to continue pulsing high and low at the right frequency, and for the CPU to continue running separately, but also schedule functions to run when the clock goes high. I ended up using **threading**, one thread for the CPU and one thread for the clock and utilise **events** to signal the clock going high and low so that it can run all the scheduled functions.

In this project I used: **Python**, **OOP** including using abstract classes, **concurrency** with **threading** and **binary code**.

### [TumbleTower](https://github.com/Ford2003/TumbleTower)

In March 2024, Discord unveiled the [Embedded Apps SDK](https://support-dev.discord.com/hc/en-us/articles/21204423970071-Introducing-the-Embedded-App-SDK), which allowed users to create web activities to be used/played in discord voice chats. They also did a competition, given about month create something using the new SDK and pitch it to Discord, there were several categories to aim to involve in your activity and 5 possible winners. I decided to join this competition and give it a go. I decided to try and make a physics based tower building game. **TumbleTower: A multiplayer experience where randomised blocks will fall from the sky in a tetris fashion and you need to build a tower to the goal and have it stay up for 5 seconds to win, however gravity and wind won't make it so easy**. This was an ambitious project to undertake for someone with limited web development experience at the time, but I was **determined**. Discord provided a couple simple example projects to build of from to help get going initially. One of which utilised: **React**, **Vite**, **Express** and **Colyseus** for a simple multiplayer experience. I spent a good 2 weeks looking deeply into every part of this code trying to wrap my head around it, having never looked at React at the time it was a real struggle to get going, and after battling with myself, wanting to give up, I persevered. Eventually, I managed to get developing. I added the [matter-js](https://github.com/liabru/matter-js) dependency for the physics engine, but how was I going to use it for multiplayer? I needed a way for every player to have a synchronised view of the game. I decided to run the actual physics engine on the server and use "mock" or "disabled" engines on the client, purely for rendering the blocks. Then when I receive a movement input from the player I send it to the server to move the block in the actual engine, and when a blocks position is updated on the actual engine then I send a multicast event to the clients with the ID's and position deltas for updating the positions of blocks the clients mock engines. Once I had this architecture in place, my development really sped up and I managed to get some features of the game in place. Including a ready-up main menu, moving blocks, spawning new blocks and removing blocks that fall below a threshold. However, it was too late to complete, polish up and add textures, etc and the competition finished, so since my project was pretty incomplete I didn't manage to win and the project has been left since. You can still reach the website [TumbleTower](https://tumble-tower.fun), but can only be played in Discord voice chats and only is you are on the developer list. 

When it came to deploying this project I used a Linux VPS and set up a firewall, Nginx server and made some build scripts to simplify the process and to avoid any mistakes, I tried to set up a simple CI/CD workflow on GitHub Actions so that when I pushed code to `main` it would automatically SSH to my VPS and run a git pull request to get the new files and then run the normal npm build script I wrote and then restart the nginx server.

In this project I used: **TypeScript**, **NodeJS**, **React**, **Express**, **Vite**, **Matter-js**, **Discord Embedded App SDK and Discord API**, **Linux**, **Nginx**, **CI/CD with GitHub Actions**, **Git**.

## Certifications
1. [Learn Python 3](https://www.codecademy.com/learn/learn-python-3)
2. [Learn Intermediate Python](https://www.codecademy.com/learn/learn-intermediate-python-3)
3. [Learn Advanced Python](https://www.codecademy.com/learn/learn-advanced-python)
4. [Build Python Web Apps with Flask](https://www.codecademy.com/learn/paths/build-python-web-apps-flask)
5. [Learn C++](https://www.codecademy.com/learn/learn-c-plus-plus)
