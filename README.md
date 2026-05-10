# 🌟 Advanced CNN Image Classifier & LR Optimization
# دسته‌بندی پیشرفته تصاویر با شبکه عصبی پیچشی و بهینه‌سازی نرخ یادگیری

<div dir="rtl">

## 📖 معرفی پروژه
این پروژه یک پیاده‌سازی کامل و حرفه‌ای برای آموزش یک مدل شبکه عصبی پیچشی (CNN) با استفاده از PyTorch است. در این پروژه، تمرکز ویژه‌ای روی تمیزکاری داده‌ها، معماری اصولی مدل و از همه مهم‌تر، **پیدا کردن بهترین نرخ یادگیری (Learning Rate)** برای رسیدن به بالاترین دقت در کمترین زمان ممکن شده است.

## ✨ ویژگی‌های کلیدی (Features)

*   🧹 **پاک‌سازی داده‌ها (Data Cleaning)**: شناسایی و حذف خودکار تصاویر تکراری برای جلوگیری از نشت داده (Data Leakage) و اورفیت شدن (Overfitting).
*   📂 **مدیریت بهینه داده‌ها (Data Loading)**: استفاده از `ImageFolder` و `DataLoader` برای بارگذاری استاندارد و بچ‌بندی داده‌ها.
*   🧠 **معماری هوشمند مدل (CNN Architecture)**: 
    *   استفاده از لایه‌های `Conv2d` به همراه `BatchNorm2d` برای تسریع همگرایی.
    *   استفاده از `Dropout` برای جلوگیری از حفظ کردن داده‌ها (Overfitting).
    *   استفاده از `AdaptiveAvgPool2d` که مدل را نسبت به تغییرات سایز تصویر ورودی منعطف می‌کند.
*   🎯 **آزمون محدوده نرخ یادگیری (LR Range Test)**: پیاده‌سازی تست محدوده LR برای یافتن نقطه طلایی یادگیری که در این پروژه عدد فوق‌العاده $7.59 \times 10^{-2}$ به دست آمد.
*   🔄 **زمان‌بندی دوره‌ای (CyclicLR)**: استفاده از زمان‌بند `CyclicLR` با حالت `triangular2` به همراه بهینه‌ساز SGD (Nesterov Momentum) برای فرود نرم و دقیق در بهینه‌ترین نقطه تابع زیان.

## 🚀 مراحل اجرای پایپ‌لاین

1.  **آماده‌سازی داده‌ها:** ابتدا تصاویر تکراری حذف شده و سپس با ابزارهای استاندارد پای‌تورچ، داده‌ها برای ورود به مدل آماده شدند.
2.  **تعریف مدل (CNN3):** مدل با لایه‌های کانولوشنال، نرمال‌سازی بچ و پولینگ تطبیقی مقداردهی اولیه شد.
3.  **تست نرخ یادگیری (LR Finder):** مدل با نرخ‌های یادگیری مختلف از بسیار کوچک ($10^{-7}$) تا بزرگ ارزیابی شد و نمودار Loss رسم شد تا بهترین شیب نزولی کشف شود.
4.  **پیکربندی نهایی آموزش:** با تنظیم `base_lr` روی $\frac{1}{10}$ مقدار پیشنهادی و تنظیم `max_lr` روی خود عدد پیشنهادی، مدل آماده‌ی یک آموزش سریع و پایدار شد.

---
</div>

<div dir="ltr">

## 📖 Project Overview
This repository contains a robust and professional pipeline for training a Convolutional Neural Network (CNN) using PyTorch. The project strongly emphasizes data sanitization, solid architectural design, and—most importantly—**Learning Rate Optimization** to achieve maximum accuracy efficiently.

## ✨ Key Features

*   🧹 **Data Cleaning**: Automated detection and removal of duplicate images to prevent data leakage and overfitting.
*   📂 **Efficient Data Loading**: Utilizing PyTorch's `ImageFolder` and `DataLoader` for standardized batching and loading.
*   🧠 **Smart Model Architecture**: 
    *   Integration of `Conv2d` and `BatchNorm2d` for faster convergence.
    *   `Dropout` layers to effectively regularize the network.
    *   `AdaptiveAvgPool2d` to make the network invariant to input size dimensions.
*   🎯 **LR Range Test**: Implementation of a learning rate finder to discover the "sweet spot" for training. In this experiment, the optimal LR was found to be $7.59 \times 10^{-2}$.
*   🔄 **Cyclic Learning Rate**: Integration of `CyclicLR` (using `triangular2` mode) alongside an SGD optimizer with Nesterov Momentum, ensuring smooth and precise convergence.

## 🚀 Pipeline Steps

1.  **Data Preparation:** Duplicates were purged, and datasets were wrapped into DataLoaders.
2.  **Model Definition (CNN3):** A custom CNN was initialized featuring convolutional blocks, batch normalization, and adaptive pooling.
3.  **LR Range Test:** The model was tested with exponentially increasing learning rates (from $10^{-7}$ upwards). The loss landscape was plotted to identify the steepest gradient, revealing the optimal LR.
4.  **Final Training Configuration:** The scheduler was configured with `base_lr` set to $1/10$ of the optimal LR and `max_lr` set to the optimal LR itself, perfectly priming the model for a highly stable and rapid training phase.

</div>
