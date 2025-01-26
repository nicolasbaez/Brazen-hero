# Brazen-hero
Stormy year

![buh](https://github.com/nicolasbaez/Brazen-hero/blob/main/xp046.gif)
```javascript
setup = (_) => createCanvas((w = 500), w);
k = 0;
draw = (_) => {
  h = w / 2;
  n = 0.01;
  clear();
  fill(h);
  rect(150, 75, 200, 350);
  fill(0);
  rect(190, 75, 10, 350);
  for (i = 150; i < 350; i++) {
    stroke(h, 0, 0, noise(i * n, k * n) * h);
    line(
      i,
      75,
      i + noise(k * n, i * n) * 75,
      map(sin(map(i + k, 150, 350, 0, 25)), -1, 1, 440, 450)
    );
  }
  if (k == 0) saveGif("xp046.gif", 512, { delay: 0, units: "frames" });
  k++;
};
