# I2P + JavaScript obfuscation

## Version

Date        | Author                  | Contact               | Version | Comment
---         | ---                     | ---                   | ---     | ---
24/11/2019  | noraj (Alexandre ZANNI) | noraj#0833 on discord | 1.0     | Document creation

Information displayed for CTF players:

+ **Name of the challenge** / **Nom du challenge**: `noraj secret zone`
+ **Category** / **Catégorie**: `Web`
+ **Tags**: _misc_ (i2p), _web-client_ (JS), _network_ (i2p), _reverse_ (JS obfuscation)
+ **Internet**: required
+ **Difficulty** / **Difficulté**: Medium / Moyen

### Description

```
The world is dark, and noraj secret zone is hidden in a dark place.

xgyvm3yn6my4ryhws5p6esd3rony336kqzjkuxpzak6q3nveiiqq.b32.i2p

Flag format: sigsegv{username:password}

author: [noraj](https://pwn.by/noraj/)
```

# Integration

**Warning**: very long to start the first time.

This challenge require a Docker Engine and Docker Compose.

Builds, (re)creates, starts, and attaches to containers for a service:

```
$ docker-compose up --build
```

Add `-d` if you want to detach the container.

## Solving

### Author solution

The given commands are for ArchLinux based systems.

1. Install i2p: `sudo pacman -S i2pd`
2. Start i2p daemon: `sudo systemctl start i2pd.service`
3. Ask for the site through i2p local proxy: `curl http://xgyvm3yn6my4ryhws5p6esd3rony336kqzjkuxpzak6q3nveiiqq.b32.i2p --proxy http://127.0.0.1:4444` or set the proxy in Firefox.
4. There is an obfuscated JS script: `_.js`
5. Use a JS deobfuscator for a first pass:
  * https://lelinhtinh.github.io/de4js/
  * http://www.jsnice.org/
  * http://deobfuscatejavascript.com/
6. Finish deobfucation manually (see `login.clean.js`)

## Flag

`sigsegv{n0r4j:sdhfisdhfuyehk}`