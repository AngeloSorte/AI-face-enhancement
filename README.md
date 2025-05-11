# AI Face Enhancement with GFPGAN

This project demonstrates how to use Tencent ARC's GFPGAN for AI-based face restoration and enhancement. It is especially useful for improving old, low-resolution, or AI-generated faces.

## 📦 Setup Instructions

1. Clone this repository.
2. Install dependencies.
3. Download the pre-trained GFPGAN model.
4. Run the face enhancement on your input image.

## 🚀 How to Use

### 1️⃣ Install Dependencies

(bash)
git clone https://github.com/TencentARC/GFPGAN.git
cd GFPGAN
pip install -r requirements.txt
python setup.py develop
wget https://github.com/TencentARC/GFPGAN/releases/download/v1.3.8/GFPGANv1.3.pth -P experiments/pretrained_models


2️⃣ Prepare an Input Image

You can upload an image manually to the working directory or fetch it from a URL using:

import requests
from PIL import Image
from io import BytesIO

url = 'https://i.imgur.com/FVLRr2o.jpg'
response = requests.get(url)
img = Image.open(BytesIO(response.content)).convert("RGB")
img.save('input.jpg')


3️⃣ Run the Enhancement

(bash)
inference_gfpgan.py --upscale 2 --test_path input.jpg --save_root results --version 1.3

4️⃣ View the Result

from PIL import Image
import matplotlib.pyplot as plt

result = Image.open('results/restored_imgs/input.jpg')
plt.imshow(result)
plt.axis('off')
plt.show()


📄 License
This project uses the GFPGAN open-source license by Tencent ARC.

## 👤 Author

**Angelo Sorte**  
AI & Software Engineer passionate about ethical AI applications and digital creativity.  
Feel free to connect or follow my work:

- LinkedIn: [your-linkedin-profile](https://linkedin.com/in/angelo-sorte)


If you use or find this project useful, feel free to star ⭐ the repository!

