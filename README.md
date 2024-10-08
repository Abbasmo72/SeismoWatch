کد پایتون برای دریافت و پردازش داده‌های زلزله
مقدمه
این کد پایتون به منظور دریافت اطلاعات مربوط به زلزله‌ها از سرویس‌های وب استفاده می‌شود. داده‌ها به فرمت JSON از وب‌سایت USGS (سازمان زمین‌شناسی ایالات متحده) دریافت می‌شوند و سپس با استفاده از تابعی به نام printResults، نتایج مرتبط با زلزله‌ها به صورت خوانا برای کاربر نمایش داده می‌شوند.

توضیح کد
کتابخانه‌های مورد استفاده
در ابتدا، دو کتابخانه json و urllib.request وارد شده‌اند. کتابخانه json برای پردازش داده‌های JSON و کتابخانه urllib.request برای ارسال درخواست‌های HTTP و دریافت داده‌ها از اینترنت استفاده می‌شود.

تابع printResults(data)
این تابع مسئول پردازش و نمایش اطلاعات زلزله‌ها است. مراحل اصلی این تابع به شرح زیر است:

بارگذاری داده‌ها: با استفاده از json.loads(data) داده‌های JSON بارگذاری می‌شوند.
چاپ عنوان: اگر عنوانی در متاداده وجود داشته باشد، عنوان آن چاپ می‌شود.
شماره‌گذاری رویدادها: تعداد رویدادهای ثبت‌شده نمایش داده می‌شود.
نمایش مکان‌ها: مکان تمامی زلزله‌ها از داده‌ها استخراج و نمایش داده می‌شود.
نمایش زلزله‌های با قدرت ۴.۰ و بیشتر: مکان زلزله‌هایی که قدرت آنها ۴.۰ یا بیشتر است، چاپ می‌شود.
رویدادهای احساس شده: در نهایت، اگر گزارشی از احساس زلزله وجود داشته باشد، مکان و تعداد دفعاتی که احساس شده است نمایش داده می‌شود.
تابع main()
تابع main وظیفه ارسال درخواست HTTP به وب‌سایت USGS و دریافت داده‌ها را بر عهده دارد:

تعریف URL: آدرس URL مربوط به داده‌های زلزله‌ها مشخص می‌شود.
ارسال درخواست: با استفاده از urllib.request.urlopen(urlData) درخواست ارسال می‌شود.
بررسی کد وضعیت: اگر کد وضعیت ۲۰۰ باشد (به معنای موفقیت)، داده‌ها خوانده و به تابع printResults ارسال می‌شوند.
مدیریت خطا: اگر کد وضعیت غیر از ۲۰۰ باشد، پیامی مبنی بر وجود خطا چاپ می‌شود.
نقطه ورود برنامه
در انتهای کد، با استفاده از if __name__ == "__main__": تابع main فراخوانی می‌شود، که این به معنای آغاز اجرای برنامه است.

نتیجه‌گیری
این کد یک ابزار ساده و کارآمد برای دریافت و نمایش اطلاعات زلزله‌ها از منابع معتبر است. با کمی تغییرات می‌توان آن را بهبود داد، مثلاً با افزودن قابلیت ذخیره‌سازی داده‌ها در یک فایل یا ارسال اعلان به کاربر در صورت وقوع زلزله‌های خاص.

با استفاده از این کد می‌توانید به راحتی از اطلاعات زلزله‌های اخیر مطلع شوید و تحلیل‌های خود را انجام دهید.

