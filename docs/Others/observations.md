Must not forget that Detectron2, Pytorch-lightning, Hugging-face transformers, and Pytorch has option to resume training.

With this resume training option, we can continuously train on colab. 


`image.shape` works in opencv
    - outputs (height, width, channels)
    
`image.size` works in PIL(pillow)
    - outputs (width,height).
    - img.mode gives no.of.channels like `RGB`.
then what is torch follows..?


if `!cd` doesn't work in colab, then try `%cd`. check [here](https://stackoverflow.com/questions/48298146/changing-directory-in-google-colab-breaking-out-of-the-python-interpreter)


Shell command in python code:
```
import subprocess

def convert_pdf_to_html(pdf_path, html_path):
    command = f"pdf2htmlEX {pdf_path} --dest-dir {html_path}"
    subprocess.call(command, shell=True)

input_pdf = "quarterly-nvidia.pdf"
output_pdf = "quarterly-nvidia"

convert_pdf_to_html(input_pdf, output_pdf)
```