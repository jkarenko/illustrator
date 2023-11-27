# image-to-text-to-other-image-to-text-to-image illustrator

## Requirements

```bash
# install requirements
pip install openai
```

## Example use
1. We want to recreate this image:

    <img style="width:200px" src=./example_images/picard.webp>

1. In the environment of this image:

    <img style="width:200px" src=./example_images/diver.jpg>

1. In this style: "ink on paper"

1. To get something like this image:

      <img style="width:200px" src=./example_images/result.png>

```
./illustrator.py --style "ink on paper" --dalle 3 --size 3 --image-quality high --hd --image-file ./example_images/picard.webp --reference-image ./example_images/diver.jpg

Encoding image: ./example_images/picard.webp
Encoding image: ./example_images/diver.jpg
Describing image...
Describing reference image...
Re-describing scene with override environment...

Details:
This image depicts a person seated in what appears to be the interior of a historic submarine or underwater exploration vehicle, evidenced by the antique and nautical instruments around. The individual, presenting as male, appears to be middle-aged to senior, roughly average in height judging by the proportion of the chair in relation to his body size. He has a bald head and is wearing a traditional deep-sea diving suit, complete with a brass helmet that is characteristic of early underwater exploration gear, with muted greenish and brown colors suggestive of wear and age from numerous undersea ventures.

His gaze is directed straight ahead, suggesting he is focusing on something or someone in front of him, through the porthole-like viewport of the diving helmet. His expression is serious and contemplative. The setting behind him is obscured by water, with bubbles rising around the helmet, creating a sense that he is submerged in a murky, underwater environment. The colors behind him are subdued, contributing to the impression of an underwater scene. No other individuals or characters are visible within this section of the image. The person's overall demeanor implies authority and calm, aligning with the typical portrayal of a seasoned diver or underwater expedition leader in a historical narrative.

Style:
ink on paper
```


## Help
```bash
./illustrator.py -h
usage: illustrator.py [-h] [--scene SCENE] [--style [STYLE]] [--dalle {2,3}] [--optimized] [--environment ENVIRONMENT] [--reference-image REFERENCE_IMAGE]
                      [--debug] [--image-url IMAGE_URL] [--image-file IMAGE_FILE] [--image-quality {high,low}] [--hd] [--detail {vivid,natural}]
                      [--size {1,2,3}] [--no-test]

options:
  -h, --help            show this help message and exit
  --scene SCENE         Scene description
  --style [STYLE]       Style description, e.g. vivid, dark, bright, surreal, realistic, cartoonish, painting-like, photorealistic, impressionistic,
                        abstract, minimalist, simplistic, complex, busy, chaotic, calm, peaceful, tranquil, serene, relaxing, tense, stressful, scary,
                        frightening, terrifying, horrifying, creepy, eerie, unsettling, disturbing, upsetting, sad, depressing, melancholic, melancholy,
                        happy, joyful, cheerful, playful, fun, funny, humorous, hilarious, amusing, entertaining, exciting, thrilling, adventurous,
                        romantic, sexy, erotic, sensual, sexual, sophisticated, elegant, classy, stylish, fashionable, trendy, modern, futuristic, retro,
                        nostalgic, old-fashioned, traditional, historic, ancient, mythological, fantasy, magical, mystical, mysterious, science-fiction,
                        sci-fi, futuristic, utopian, dystopian, apocalyptic, post-apocalyptic, cyberpunk, steampunk, gothic, medieval, western, noir, film-
                        noir, noirish, gritty, dark, grim, gruesome, macabre, morbid, grotesque, horror, horror-like, horror-themed, horror-inspired
  --dalle {2,3}         Choose Dall-e version, either '2' or '3'
  --optimized           Create an additional optimized prompt for Dall-e
  --environment ENVIRONMENT
                        Environment override, e.g. 'a fantasy world'
  --reference-image REFERENCE_IMAGE
                        Reference image for the illustration
  --debug               Enable debug mode
  --size {1,2,3}        1=portrait (1024x1792) or small (256x256), 2=landscape (1792x1024) or medium (512x512), 3=square (1024x1024), default=3
  --no-test             Disable test mode prompt hack

Image to text settings:
  --image-url IMAGE_URL
                        Use image at URL as scene descriptor
  --image-file IMAGE_FILE
                        Use image file as scene descriptor
  --image-quality {high,low}
                        Image quality used during image to text, either 'high' or 'low'

Dall-e 3 specific settings:
  --hd                  High definition mode for more detailed images
  --detail {vivid,natural}
                        Detail level, either 'vivid' or 'natural'
```
