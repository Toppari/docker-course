# Flow

Starting in **Terminal 1** start container with ubuntu image with the requested process.

When **Terminal 1** asks for website, open **Terminal 2** to install curl inside the container.

After installing curl inside the container, switch back to **Terminal 1** to complete the exercise.

## Terminal 1

```console
$ docker container run --name missing -it ubuntu sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="https://www.helsinki.fi/">here</a>.</p>
</body></html>
```

## Terminal 2

```console
$ docker exec -it missing bash
root@88b554680cf0:/# apt update
root@88b554680cf0:/# apt install curl
```
