# Raspian Shrink

Shrinks a Raspberry Pi Raspbian SD card image

## Docker image build

```sh
docker build -t kscape/raspbian-shrink .
```

### Shrink image

```sh
docker run --rm -it -v "$(pwd)":/work-dir --privileged kscape/raspbian-shrink original.img shrunken.img
```

Or add this to you .bashrc :

```sh
shrink()
{
   docker run --rm \
       -it \
       -v "`pwd`":/work-dir \
       --privileged
       kscape/rapbian-shrink "$@"
}
```

Then run `shrink original.img shrunken.img` directly from the terminal to resize some image