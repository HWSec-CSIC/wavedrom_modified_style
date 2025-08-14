## Introduction

This is a fork of the original repository of the **WaveDrom**. The idea is to modify *skins* to generate different styles. 

## Usage

### HTML page

There are several examples in ```work_folder```: 

1) Put the following line into your HTML page ```<header>```:

```html
<script src=".../skins/default.js" type="text/javascript"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/wavedrom/3.1.0/wavedrom.min.js" type="text/javascript"></script>
```

2) Set the ``onload`` event for the HTML body.

```html
<body onload="WaveDrom.ProcessAll()">
```

3) Insert [WaveJSON](https://github.com/wavedrom/schema/blob/master/WaveJSON.md) source inside HTML ``<body>`` wrapped with the ``<script>`` tag:

```html
<script type="WaveDrom">
{ signal : [
  { name: "clk",  wave: "p......" },
  { name: "bus",  wave: "x.34.5x",   data: "head body tail" },
  { name: "wire", wave: "0.1..0." },
]}
</script>
```

## Modify your skin

1) To modify your skin, first generate a new one. There is an example of it in ```unpacked/skins/default_noX.svg``` where the X values have been translated into black spaces.

2) For the next step you need to install node: 
```bash
sudo apt install nodejs
```
If you don't have some package. First you have to type:
```bash
sudo apt install npm
```
and then:
```bash
sudo npm install <package_name>
```

3) Run:
 ```bash
 sudo nodejs bin/svg2js.js -i unpacked/skins/default_noX.svg > skins/default_noX.js
 ```

 4) Then change your HTML to:
```html
<script src=".../skins/default_noX.js" type="text/javascript"></script>
<script src=".../wavedrom.min.js" type="text/javascript"></script>
``` 

## License

See [LICENSE](https://github.com/wavedrom/wavedrom/blob/master/LICENSE).
