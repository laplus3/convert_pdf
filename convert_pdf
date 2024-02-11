from PIL import Image
from reportlab.pdfgen import canvas
import os

def convert_images_to_pdf(image_folder, output_pdf):
    # 画像フォルダ内のファイルを取得
    image_files = [f for f in os.listdir(image_folder) if f.lower().endswith(".png")]

    if not image_files:
        print("PNG画像が見つかりませんでした。")
        return

    # PDF生成
    with open(output_pdf, "wb") as pdf_file:
        pdf = canvas.Canvas(pdf_file)

        for image_file in image_files:
            image_path = os.path.join(image_folder, image_file)
            img = Image.open(image_path)
            width, height = img.size

            # PDFページサイズを画像サイズに合わせて設定
            pdf.setPageSize((width, height))


            # 画像をPDFに追加
            pdf.drawInlineImage(image_path, 0, 0, width, height)

            # ページを追加（必要に応じて調整）
            pdf.showPage()

        pdf.save()

    print(f"PDFファイル '{output_pdf}' が作成されました。")

image_folder_path = r""
    
    # 生成されるPDFファイルのパス
output_pdf_path = r""

convert_images_to_pdf(image_folder_path, output_pdf_path)
