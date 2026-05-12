
**Turn .png images in a folder into a webp**

for img in *.png; do
  ffmpeg -i "$img" "${img%.png}.webp"
done

**turn the webp into incrementally growing image names**

i=1
for img in *.webp; do
  [[ -e "$img" ]] || continue
  mv "$img" "${i}.webp"
  ((i++))
done


