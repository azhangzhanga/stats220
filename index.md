# stats220 assignment 1
## My motivation for this project 
*keep passion for learning and for statistics at all times.*

## About my meme
**The meme is an adaption of an existing meme format**. 

Below is a meme I created using the R package {[magick](https://cran.r-project.org/web/packages/magick/index.html)}. 

![meme](https://github.com/azhangzhanga/stats220/blob/main/meme.png?raw=true). 

The summary of my inspiration for the meme is:  
1. reminding studying is funny
2. maintaining a passion for stats

Below is R code I used to make the meme.  

```r  

spongebob <- image_read("https://www.meme-arsenal.com/memes/fa7b53bcba06aacf272958d3ae04ae46.jpg") %>%
  image_scale(500)


study_text <- image_blank(width = 500, 
                          height = 500, 
                          color = "#000000") %>%
  image_annotate(text = "Studying is fun",
                 color = "#FFFFFF",
                 size = 60,
                 font = "Impact",
                 gravity = "center")


tony <- image_read("https://www.meme-arsenal.com/memes/588cb069592452731ffff3e4c2014d36.jpg") %>%
  image_scale(500)


stats_text <- image_blank(width = 500, 
                       height = 500, 
                       color = "#000000") %>%
  image_annotate(text = "Oh, I love stats!",
                 color = "#FFFFFF",
                 size = 60,
                 font = "Impact",
                 gravity = "center")


spongebob_vector <- c(spongebob, study_text)
top_row <- image_append(spongebob_vector)


bottom_row <- image_append(c(tony, stats_text))


c(top_row, bottom_row) %>%
  image_append(stack = TRUE) %>%
  image_scale(800)
```
