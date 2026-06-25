# Video assets

Drop your `.mp4` clips here. They are served from the site root under `/videos/`.
All players are muted + looping, so short (5–20 s), web-optimized H.264 clips work best.

Recommended encode:
```bash
ffmpeg -i input.mov -vcodec libx264 -crf 24 -pix_fmt yuv420p -an -movflags +faststart output.mp4
```

## Files the site expects

| Filename                     | Where it shows                              |
|------------------------------|---------------------------------------------|
| `vla-humanoid-demo.mp4`      | Full-screen hero background on the homepage |
| `vla-humanoid-poster.jpg`    | Hero poster (shown before the video loads)  |
| `go2-navigation.mp4`         | Featured Work showcase card                 |
| `moonbot.mp4`                | Featured Work showcase card                 |
| `drone-ekf.mp4`              | Featured Work showcase card                 |
| `humanoid-sim.mp4`           | Featured Work showcase card                 |

Each showcase card has an animated gradient fallback, so missing files degrade
gracefully — the layout never looks broken while you collect footage.
