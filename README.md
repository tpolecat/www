

# Rob's Website

### Content Compression - Images

- Export `.png` with max width 1024
- For existing files that may be larger, `sips --resampleWidth 1024 *.png`

### Content Compression - Video

- Export at 720p
- Convert to `.mp4` with

```bash
for file in *.mov; do
    ffmpeg -i "$file" -c:v libx264 -crf 26 -preset slower -pix_fmt yuv420p -movflags +faststart -c:a aac -b:a 128k "${file%.mov}.mp4"
done
```

For some reason this won't work as a shell script.

