# Convert rtf Documents

Converts an rtf document to html, text or latex. Output in html is
recommended because `unrtf` has limited support for converting between
character encodings which is problematic for non-ascii text.

## Usage

``` r
unrtf(
  file = NULL,
  format = c("html", "text", "latex"),
  verbose = FALSE,
  conf_dir = NULL
)
```

## Arguments

- file:

  path or url to the 'rtf' file

- format:

  output format, must be "text", "html" or "latex"

- verbose:

  print some output to stderr

- conf_dir:

  use a custom dir with `.conf` files which serve as output templates.

## Details

Output can be customized via a set of `.conf` files which serve as
templates for the various formats. The default conf files are located in
`system.file("share", package = "unrtf")` To modify the output, copy
these files to a custom location and set pass the directory as the
`conf_dir` argument in `unrtf`.

## Examples

``` r
# \donttest{
library(unrtf)
text <- unrtf("https://jeroen.github.io/files/sample.rtf", format = "text")
html <- unrtf("https://jeroen.github.io/files/sample.rtf", format = "html")
cat(text)
#> ###  Translation from RTF performed by UnRTF, version 0.21.9 
#> ### font table contains 11 fonts total
#> 
#> TITLE: It is an example test rtf-file to RTF2XML bean for testing
#> 
#> AUTHOR: kissj
#> ### creation date: 17 April 2000 15:34 
#> ### revision date: 19 April 2000 09:34 
#> ### total pages: 2
#> ### total words: 217
#> ### total chars: 1240
#> 
#> -----------------
#> It is an example test rtf-file to RTF2XML bean for testing
#> 
#> Font size 10, plain text;
#> Font size 12, bold text. Underline,bold text.
#>  Underline,italic,bold text. 
#> Font size 22, plain text.
#>  Bold text.
#>         
#>         
#>         
#>  Italic text.
#> 
#>  Simple table :
#> 
#> 
#> 
#>  1st column  2nd column  3rd column  4th column  5th column  
#>  1.1 item    1.2 item    1.3 item    1.4 item    1.5 item    
#>  2.1 item    2.2 item    2.3 item    2.4 item    2.5 item    
#>  3.1 item    3.2 item    3.3 item    3.4 item    3.5 item    
#>  4.1 item    4.2 item    4.3 item    4.4 item    4.5 item    
#>  5.1 item    5.2 item    5.3 item    5.4 item    5.5 item    
#>  Empty   &&  &       Empty   
#>  Last items& &   &       Last items  
#> 
#> 
#> 
#> List :
#> 
#> "        
#> It is the 1st row of the list
#> "        
#> It is the 2nd row of the list
#> "        
#> &
#> "        
#> &
#> "        
#> &
#> "        
#> It is the last row of the list
#> 
#>  Here is a brief Courier text.
#>  Here is a brief MS Sans - Serif text.
#>  Here is a brief MS Serif text.
#>  Here is a brief Times New Roman text.
#> 
#>  
#> 
#>  Some paragraphs :
#> 
#> I.      
#> Align left :
#> 
#>  The text you are reading is aligned left. It is an align  left text. It is also an align  left sentence. 
#>  
#> II.     
#> Align right:
#> 
#>  The text you are reading is aligned right. It is an align  right text. It is also an align  right sentence. 
#> 
#> III.    
#> Align centered:
#> 
#>  The text you are reading is aligned center. It is an align  centered text. It is also an align  centered sentence. 
#> 
#> IV.     
#> Align justified:
#> 
#>  The text you are reading is aligned justify. It is an align  justified text. It is also an align  justified sentence.
#> 
#> Here are some special characters: öt árvíztqrQ ütvefúrógép, which means five flood resistant hammer drills (J) in Hungarian.
#> 
#>  At last you can see an image :
#> 
#> ### Drawn Shape (ignored-not implemented yet)
#> 
#> 
# }
```
