# WebProgramming-final-research


<div dir='rtl'>
<h1>کافکا</h1>

<h2>
تاریخچه
</h2>

<h4>
آپاچی کافکا در ابتدا توسط لینکدین  توسعه یافت و در اوایل سال 2011 بصورت نرم افزار متن باز در آمد. در نوامبر ۲۰۱۴ ، چندین مهندس که در لینکدین  بر روی کافکا کار می‌کردند یک شرکت جدید به نام Confluent  ایجاد کرده و به صورت انحصاری بر روی توسعه کافکا کار کردند. بر اساس یک پست در سال 2014 به نظر می رسد که جی کربس نام این برنامه را از نام فرانتس کافکا نویسنده آلمانی برداشت کرده است.
</h4>
</br>
</br>

<h2>
آپاچی کافکا چیست؟
</h2>

<h4>
آپاچی کافکا یک پلتفرم توزیع‌شده برای پردازش داده های جریانی بوده و قادر به رسیدگی و پردازش چندین تریلیون رویداد است به صورت همزمان است. کافکا در ابتدا به عنوان یک ابزار برای ارسال پیامهایی با تعداد بالا بکار برده می شد. کافکا از زمان ایجاد و منبع باز شدن توسط لینکدین در سال ۲۰۱۱ ، به سرعت از ارسال پیام به یک پلتفرم پردازش توزیعی کامل تبدیل شده است.

آپاچی کافکا، به عنوان یک پلتفرم داده های در جریان، دارای قابلیتهایی ازقبیل زمان پاسخ کوتاه، کارایی بالاو تحمل خطا بوده و قادر به پردازش جریانهایی سریع از رویدادها می باشد. کافکا، برای پشتیبانی از برنامه های کاربردی مشتری و اتصال سیستم های پایین دست با داده های زمان واقعی پاسخ های در حد میلی ثانیه فراهم می کند.

</h4>
</br>
</br>

<h2>
کاربرد های کافکا
</h2>

<h4>
<ul>
<li>
ایجاد خطوط انتقال داده های جریانی و به هنگام که داده ها را میان سیستمها و برنامه ها بصورت قابل اطمینانی انتقال داده و رد و بدل می کند.
</li>
<li> ایجاد برنامه های کاربردی برای داده های جریانی و به هنگام که به موقع نسبت به جریانی از داده ها واکنش نشان داده و آنها را انتقال می دهد.</li>
</ul>
</h4>
</br>
</br>

<h2>
ساختار و نحوه کار کافکا
</h2>

<h4>
قبل از اینکه به ساختار کافکا بپردازیم ابتدا چند اصطلاح را توضیح می دهیم:

 <li>
 کافکا به صورت خوشه ای بر روی یک یا چند سرور کار می کند
 </li>

  <li>
 کافکا جریان داده ها و رکورد ها را در ساختارهایی به نام تاپیک( topics) ذخیره می کند
 </li>

  <li>
  هر رکوردی دارای یک کلید، یک مقدار و یک برچسب زمانی می باشد تا بصورت مجزا از سایر رکورد ها مشخص باشد
 </li>

</br>
 کافکا دارای 4 رابط کاربری برای برنامه خود می باشد که هر کدام نقشی در مجموعه فعالیتهای کافکا دارند. این رابطها شامل:

  <li>
  رابط تولید کننده (Producer) که به یک برنامه اجازه می دهد رشته هایی از رکورد ها را بر روی یک یا چند تاپیک کافکا منتشر کند
 </li>

  <li>
   رابط مصرف کننده(Consumer) که به یک برنامه اجازه می دهد به یک یا چند تاپیک متصل شده و رکورهای موجود را پردازش کند
 </li>
  <li>
  رابط جریانی (Streams) که به یک برنامه اجازه می دهد بصورت پردازشگر داده های جریانی عمل کرده و داده های ورودی موجود بر یک یا چند تاپیک را مصرف کرده و خروجی آن نیز تولید جریانی از داده ها بر روی تاپیکهای خروجی بوده و بصورت موثری جریانهای ورودی را به خروجی تبدیل می کند.
 </li>

  <li>
   رابط اتصال دهنده(Connector) که اجازه ساخت و اجرای تولید کننده ها و مصرف کننده هایی با قابلیت استفاده مجدد را می دهد که تاپیکهای کافکا را به برنامه ها و سیستمهای داده ای موجود متصل می کند. مثلا یک اتصال دهنده به یک پایگاه داده رابطه ای می تواند هر نوع تغییری که بر روی یک جدول اعمال شده را ثبت و ضبط کند.  
 </li>
شکل زیر رابط های کاربری و نحوه کار کافکا را بصورت شماتیک نشان می دهد.

<img src='./neda/one.JPG'>

</br>
بطور کلی نحوه کار کافکا بصورت ذیل است:

کافکا پیامهایی را که از بسیاری از "تولید کنندگان" دریافت می کند را ذخیره کرده و داده ها بدین صورت بر روی پارتیشن های گوناگونی در "تاپیکهای" مختلف توزیع شده و پارتیشن بندی می شوند. در هر پارتیشن پیامها با هم شاخص گذاری شده و با یک برچسب زمانی ذخیره می شوند. سایر فرایندها مثل "مصرف کنندگان" می توانند پیامها را از پارتیشنها دریافت کرده و اطلاعات مورد نظر خود را درخواست کنند. کافکا بر روی خوشه هایی از یک یا چند سرور اجرا می شود و پارتیشنها می توانند بر روی چندین نود مختلف توزیع شوند.

آپاچی کافکا هنگامی که همراه با آپاچی استورم، اچ بیس و اسپارک استفاده شود به طور موثری می تواند داده‌های بلادرنگ و جریان را پردازش کند. اگر کافکا به عنوان یک خوشه روی چندین سرور پیکر بندی و اجرا شود در اینصورت به کمک 4 رابط کاربری خود براحتی عملیات انتشار و دریافت و پردازش اطلاعات را به سرعت و با کارایی بالا انجام می دهد.

توانایی کافکا برای ارایه جریان‌های عظیم داده و پیام ،همراه با تحمل خطای بالا ، آن را جایگزین برخی از سیستم‌های پیام‌رسانی مرسوم مانند JMS ، AMQPو غیره کرده است.

</h4>
</br>
</br>

<h2>
جریان رویداد چیست؟
</h2>

<h4>
جریان رویداد معادل دیجیتالی سیستم عصبی مرکزی بدن انسان است. این پایه تکنولوژیکی برای دنیای «همیشه فعال» است که در آن کسب‌وکارها به طور فزاینده‌ای توسط نرم‌افزار تعریف و خودکار می‌شوند، و در آن کاربر نرم‌افزار بیشتر نرم‌افزار است.

از نظر فنی، جریان رویداد عملی است که داده‌ها را در زمان واقعی از منابع رویداد مانند پایگاه‌های داده، حسگرها، دستگاه‌های تلفن همراه، سرویس‌های ابری و برنامه‌های نرم‌افزاری در قالب جریان رویدادها ضبط می‌کند. ذخیره سازی این جریان های رویداد به صورت بادوام برای بازیابی بعدی. دستکاری، پردازش، و واکنش به جریان رویداد در زمان واقعی و همچنین به صورت گذشته نگر. و مسیریابی جریان رویداد به فن آوری های مختلف مقصد در صورت لزوم. بنابراین جریان رویداد جریان و تفسیر مداوم داده ها را تضمین می کند تا اطلاعات مناسب در مکان مناسب و در زمان مناسب باشد.

</h4>
</br>
</br>

<h2>
برای چه چیزی می توانم از جریان رویداد استفاده کنم؟
</h2>

<h4>
جریان رویداد برای طیف گسترده ای از موارد استفاده در بسیاری از صنایع و سازمان ها اعمال می شود. نمونه های فراوان آن عبارتند از:

برای پردازش پرداخت ها و تراکنش های مالی در زمان واقعی، مانند بورس ها، بانک ها و بیمه ها.

برای ردیابی و نظارت بر خودروها، کامیون ها، ناوگان و محموله ها در زمان واقعی، مانند لجستیک و صنعت خودرو.

برای گرفتن و تجزیه و تحلیل مداوم داده های حسگر از دستگاه های IoT یا سایر تجهیزات، مانند کارخانه ها و پارک های بادی.

برای جمع آوری و واکنش فوری به تعاملات و سفارشات مشتری، مانند خرده فروشی، صنعت هتل و مسافرت، و برنامه های کاربردی تلفن همراه.
برای نظارت بر بیماران در مراقبت های بیمارستانی و پیش بینی تغییرات در شرایط برای اطمینان از درمان به موقع در مواقع اضطراری.

برای اتصال، ذخیره و در دسترس قرار دادن داده های تولید شده توسط بخش های مختلف یک شرکت.

به عنوان پایه ای برای پلتفرم های داده، معماری های رویداد محور و میکروسرویس ها خدمت کند.

</h4>
</br>
</br>

<h2>
Kafka APIs
</h2>

<h4 dir='rtl'>
علاوه بر ابزار خط فرمان برای وظایف مدیریت و مدیریت، کافکا دارای پنج API اصلی برای جاوا و اسکالا است:

ادمین ای پی آی برای مدیریت و بازرسی موضوعات، کارگزاران و سایر اشیاء کافکا.
API تولیدکننده برای انتشار (نوشتن) جریانی از رویدادها در یک یا چند موضوع کافکا.
Consumer API برای اشتراک (خواندن) یک یا چند موضوع و پردازش جریان رویدادهای تولید شده برای آنها.
Kafka Streams API برای پیاده‌سازی برنامه‌های پردازش جریانی و میکروسرویس‌ها. این توابع سطح بالاتری را برای پردازش جریان های رویداد ارائه می دهد، از جمله تبدیل ها، عملیات حالت دار مانند تجمیع ها و پیوستن ها، پنجره سازی، پردازش بر اساس زمان رویداد و موارد دیگر. ورودی از یک یا چند موضوع خوانده می شود تا خروجی به یک یا چند موضوع تولید شود و به طور موثر جریان های ورودی را به جریان های خروجی تبدیل کند.
Kafka Connect API برای ساخت و اجرای اتصالات واردات/صادرات داده های قابل استفاده مجدد که جریان هایی از رویدادها را از و به سیستم ها و برنامه های خارجی مصرف (خواندن) یا تولید (نوشتن) می کنند تا بتوانند با کافکا یکپارچه شوند. به عنوان مثال، یک اتصال دهنده به یک پایگاه داده رابطه ای مانند PostgreSQL ممکن است هر تغییری را در مجموعه ای از جداول ثبت کند. با این حال، در عمل، شما معمولاً نیازی به پیاده سازی کانکتورهای خود ندارید، زیرا جامعه کافکا در حال حاضر صدها کانکتور آماده برای استفاده را ارائه می دهد.

</h4>
</br>
</br>

<h2>Messaging</h2>
<h4>
کافکا به عنوان جایگزینی برای یک واسطه پیام سنتی تر به خوبی عمل می کند. واسطه‌های پیام به دلایل مختلفی (برای جدا کردن پردازش از تولیدکنندگان داده، بافر کردن پیام‌های پردازش نشده و غیره) استفاده می‌شوند. در مقایسه با اکثر سیستم های پیام رسانی، کافکا دارای توان عملیاتی، پارتیشن بندی داخلی، تکرار و تحمل خطای بهتری است که آن را به یک راه حل خوب برای کاربردهای پردازش پیام در مقیاس بزرگ تبدیل می کند.
در تجربه ما، استفاده از پیام‌رسانی اغلب نسبتاً کم توان است، اما ممکن است به تأخیر انتها به انتها کم نیاز داشته باشد و اغلب به تضمین‌های دوام قوی که کافکا ارائه می‌کند بستگی دارد.

در این حوزه کافکا با سیستم های پیام رسانی سنتی مانند ActiveMQ یا RabbitMQ قابل مقایسه است.

</h4>
</br>
</br>

<h2>معیارها</h2>
<h4>
کافکا اغلب برای داده های نظارت عملیاتی استفاده می شود. این شامل جمع آوری آمار از برنامه های کاربردی توزیع شده برای تولید فیدهای متمرکز داده های عملیاتی است.
تجمیع ورود به سیستم
بسیاری از مردم از کافکا به عنوان جایگزینی برای راه حل تجمع سیاهه ها استفاده می کنند. تجمیع گزارش‌ها معمولاً فایل‌های گزارش فیزیکی را از سرورها جمع‌آوری می‌کند و آنها را برای پردازش در یک مکان مرکزی (یک سرور فایل یا HDFS) قرار می‌دهد. کافکا جزئیات فایل‌ها را خلاصه می‌کند و انتزاعی تمیزتر از داده‌های گزارش یا رویداد را به عنوان جریانی از پیام‌ها ارائه می‌کند. این امکان پردازش با تأخیر کمتر و پشتیبانی آسان تر از منابع داده های متعدد و مصرف داده های توزیع شده را فراهم می کند. در مقایسه با سیستم‌های log-centric مانند Scribe یا Flume، کافکا عملکرد به همان اندازه خوب، تضمین‌های دوام قوی‌تر به دلیل تکرار، و تأخیر انتها به انتها بسیار کمتر را ارائه می‌دهد.
</h4>
</br>
</br>

<h2>پردازش جریان</h2>
<h4>
بسیاری از کاربران کافکا داده‌ها را در خطوط لوله پردازش متشکل از چند مرحله پردازش می‌کنند، که در آن داده‌های ورودی خام از موضوعات کافکا مصرف می‌شود و سپس تجمیع، غنی‌سازی می‌شود یا به‌طور دیگری به موضوعات جدید برای مصرف بیشتر یا پردازش بعدی تبدیل می‌شود. برای مثال، یک خط لوله پردازش برای توصیه مقالات خبری ممکن است محتوای مقاله را از فیدهای RSS بخزد و آن را در یک موضوع "مقالات" منتشر کند. پردازش بیشتر ممکن است این محتوا را عادی یا تکراری کند و محتوای مقاله پاک شده را در یک موضوع جدید منتشر کند. در مرحله نهایی پردازش ممکن است سعی شود این محتوا به کاربران توصیه شود. چنین خطوط لوله پردازشی نمودارهایی از جریان داده های بلادرنگ را بر اساس موضوعات فردی ایجاد می کند. با شروع نسخه 0.10.0.0، یک کتابخانه پردازش جریانی سبک اما قدرتمند به نام Kafka Streams در آپاچی کافکا برای انجام چنین پردازش داده‌ای همانطور که در بالا توضیح داده شد در دسترس است. به غیر از Kafka Streams، ابزارهای جایگزین متن باز پردازش جریان شامل Apache Storm و Apache Samza هستند.
</h4>
</br>
</br>

<h2>
خب حالا بریم سراف شروع کار با کافکا
</h2>

<h4>
مرحله 1: کافکا را دریافت کنید
آخرین نسخه کافکا را دانلود کنید و آن را استخراج کنید:

میتوانید از لینک زیر هم دانلود کنید

[DOWNLOAD](https://www.apache.org/dyn/closer.cgi?path=/kafka/3.4.0/kafka_2.13-3.4.0.tgz)

</h4>

```
$ tar -xzf kafka_2.13-3.4.0.tgz
$ cd kafka_2.13-3.4.0
```

<h4>
مرحله 2: محیط کافکا را شروع کنید
توجه: محیط محلی شما باید Java 8+ را نصب کرده باشد.

آپاچی کافکا را می توان با استفاده از ZooKeeper یا KRaft راه اندازی کرد. برای شروع با هر یک از پیکربندی ها یکی از بخش های زیر را دنبال کنید اما نه هر دو را.

</h4>

<h2>
کافکا با ZooKeeper
</h2>

<h4>
دستورات زیر را اجرا کنید تا همه سرویس ها به ترتیب درست شروع شوند:
</h4>

```
# Start the ZooKeeper service
$ bin/zookeeper-server-start.sh config/zookeeper.properties
```

<p>ترمینال دیگری را باز کنید و کد زیر را اجرا کنید</p>

```
# Start the Kafka broker service
$ bin/kafka-server-start.sh config/server.properties
```

<p>
هنگامی که همه سرویس ها با موفقیت راه اندازی شدند، یک محیط اولیه کافکا در حال اجرا و آماده برای استفاده خواهید داشت.
</p>

</br>
</br>

<h2 dir='ltr'>
Kafka with KRaft
</h2>

<h4>
یک Cluster UUIDایجاد کنید و کد زیر را اجرا کنید

```
$ KAFKA_CLUSTER_ID="$(bin/kafka-storage.sh random-uuid)"
```

سپس فهرست راهنماها را قالب بندی کنید

```
$ bin/kafka-storage.sh format -t $KAFKA_CLUSTER_ID -c config/kraft/server.properties
```

سرور کافکا را راه اندازی کنید

```
$ bin/kafka-server-start.sh config/kraft/server.properties
```

هنگامی که سرور کافکا با موفقیت راه اندازی شد، یک محیط اولیه کافکا در حال اجرا و آماده برای استفاده خواهید داشت.

مرحله 3: یک موضوع برای ذخیره رویدادهای خود ایجاد کنید
کافکا یک پلتفرم پخش رویداد توزیع شده است که به شما امکان می‌دهد رویدادها را بخوانید، بنویسید، ذخیره کنید و پردازش کنید (که رکوردها یا پیام‌ها در اسناد نیز نامیده می‌شوند) در بسیاری از ماشین‌ها.

رویدادهای مثال عبارتند از تراکنش‌های پرداخت، به‌روزرسانی‌های موقعیت جغرافیایی از تلفن‌های همراه، سفارش‌های حمل و نقل، اندازه‌گیری حسگر از دستگاه‌های IoT یا تجهیزات پزشکی و موارد دیگر. این رویدادها در موضوعات سازماندهی و ذخیره می شوند. بسیار ساده شده، یک موضوع شبیه به یک پوشه در یک سیستم فایل است و رویدادها فایل‌های موجود در آن پوشه هستند.

حال باید در ترمینال دیگری کد زیر را اجرا نمایید.

```
$ bin/kafka-topics.sh --create --topic quickstart-events --bootstrap-server localhost:9092
```

همه ابزارهای خط فرمان کافکا دارای گزینه های اضافی هستند: دستور kafka-topics.sh را بدون هیچ آرگومانی برای نمایش اطلاعات استفاده اجرا کنید.

```
$ bin/kafka-topics.sh --describe --topic quickstart-events --bootstrap-server localhost:9092
Topic: quickstart-events        TopicId: NPmZHyhbR9y00wMglMH2sg PartitionCount: 1       ReplicationFactor: 1	Configs:
    Topic: quickstart-events Partition: 0    Leader: 0   Replicas: 0 Isr: 0

```

مرحله 4: برخی از رویدادها را در موضوع بنویسید
مشتری کافکا برای نوشتن (یا خواندن) رویدادها از طریق شبکه با کارگزاران کافکا ارتباط برقرار می کند. پس از دریافت، کارگزاران رویدادها را تا زمانی که شما نیاز دارید - حتی برای همیشه - به روشی بادوام و بدون عیب ذخیره می کنند.

برای نوشتن چند رویداد در موضوع خود، کلاینت سازنده کنسول را اجرا کنید. به‌طور پیش‌فرض، هر خطی که وارد می‌کنید منجر به نوشتن یک رویداد جداگانه برای موضوع می‌شود.

```
$ bin/kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092
This is my first event
This is my second event
```

مرحله 5: رویدادها را بخوانید

```
$ bin/kafka-console-consumer.sh --topic quickstart-events --from-beginning --bootstrap-server localhost:9092
This is my first event
This is my second event
```

به راحتی آزمایش کنید: به عنوان مثال، برای نوشتن رویدادهای اضافی به پایانه تولیدکننده خود (مرحله قبلی) برگردید و ببینید که چگونه رویدادها بلافاصله در پایانه مصرف کننده شما نشان داده می شوند.

از آنجایی که رویدادها به طور پایدار در کافکا ذخیره می شوند، می توانند به تعداد دفعات و هر تعداد مصرف کننده که بخواهید خوانده شوند. با باز کردن یک جلسه ترمینال دیگر و اجرای مجدد دستور قبلی، به راحتی می توانید این موضوع را تأیید کنید.

مرحله 6: داده های خود را به عنوان جریان رویدادها با اتصال کافکا وارد یا صادر کنید
احتمالاً در سیستم‌های موجود مانند پایگاه‌های داده رابطه‌ای یا سیستم‌های پیام‌رسان سنتی، همراه با بسیاری از برنامه‌هایی که قبلاً از این سیستم‌ها استفاده می‌کنند، داده‌های زیادی دارید. Kafka Connect به شما اجازه می دهد تا به طور مداوم داده های سیستم های خارجی را به کافکا وارد کنید و بالعکس. این یک ابزار توسعه پذیر است که کانکتورهایی را اجرا می کند که منطق سفارشی را برای تعامل با یک سیستم خارجی پیاده سازی می کند. بنابراین، ادغام سیستم های موجود با کافکا بسیار آسان است. برای آسان‌تر کردن این فرآیند، صدها کانکتور از این قبیل به راحتی در دسترس هستند.

در این شروع سریع، نحوه اجرای Kafka Connect را با کانکتورهای ساده ای خواهیم دید که داده ها را از یک فایل به یک موضوع کافکا وارد می کند و داده ها را از یک موضوع کافکا به یک فایل صادر می کند.

ابتدا مطمئن شوید که connect-file-3.4.0.jar را به ویژگی plugin.path در پیکربندی Connect worker اضافه کنید. برای این شروع سریع، از یک مسیر نسبی استفاده می کنیم و بسته کانکتورها را به عنوان یک uber jar در نظر می گیریم، که زمانی کار می کند که دستورات شروع سریع از دایرکتوری نصب اجرا شوند. با این حال، شایان ذکر است که برای استقرار تولید، استفاده از مسیرهای مطلق همیشه ارجحیت دارد. برای توضیح دقیق نحوه تنظیم این پیکربندی به plugin.path مراجعه کنید.

فایل config/connect-standalone.properties را ویرایش کنید، ویژگی پیکربندی plugin.path را با موارد زیر اضافه یا تغییر دهید و فایل را ذخیره کنید:

```
> echo "plugin.path=libs/connect-file-3.4.0.jar"
```

سپس، با ایجاد برخی از داده های اولیه برای آزمایش شروع کنید:

```
> echo -e "foo\nbar" > test.txt
```

یا در ویندوز:

```
> echo foo> test.txt
> echo bar>> test.txt
```

در مرحله بعد، دو کانکتور را در حالت مستقل اجرا می کنیم، به این معنی که آنها در یک فرآیند واحد، محلی و اختصاصی اجرا می شوند. ما سه فایل پیکربندی را به عنوان پارامتر ارائه می کنیم. اولین مورد همیشه پیکربندی فرآیند اتصال کافکا است که شامل پیکربندی رایج مانند کارگزاران کافکا برای اتصال به و قالب سریال سازی برای داده ها است. فایل های پیکربندی باقیمانده هر کدام یک کانکتور برای ایجاد مشخص می کنند. این فایل ها شامل یک نام کانکتور منحصر به فرد، کلاس اتصال دهنده برای نمونه سازی و هر پیکربندی دیگر مورد نیاز کانکتور هستند.

```
> bin/connect-standalone.sh config/connect-standalone.properties config/connect-file-source.properties config/connect-file-sink.properties
```

این فایل‌های پیکربندی نمونه، همراه با کافکا، از پیکربندی کلاستر محلی پیش‌فرض که قبلاً شروع کرده‌اید استفاده می‌کنند و دو رابط ایجاد می‌کنند: اولی یک رابط منبع است که خطوط را از یک فایل ورودی می‌خواند و هر کدام را به یک موضوع کافکا تولید می‌کند و دومی یک رابط سینک است. که پیام های یک موضوع کافکا را می خواند و هر کدام را به صورت یک خط در یک فایل خروجی تولید می کند.

در طول راه‌اندازی، تعدادی پیام گزارش مشاهده خواهید کرد، از جمله برخی از آنها که نشان می‌دهند اتصال‌دهنده‌ها در حال نمونه‌سازی هستند. هنگامی که فرآیند اتصال کافکا شروع شد، کانکتور منبع باید شروع به خواندن خطوط از test.txt و تولید آنها به تست اتصال مبحث کند، و رابط سینک باید شروع به خواندن پیام‌ها از تست اتصال موضوع کند و آنها را در آزمون فایل بنویسد. .sink.txt. با بررسی محتویات فایل خروجی می‌توانیم تأیید کنیم که داده‌ها از طریق کل خط لوله تحویل داده شده است:

```
> more test.sink.txt
foo
bar
```

توجه داشته باشید که داده‌ها در تست اتصال موضوع کافکا ذخیره می‌شوند، بنابراین می‌توانیم یک مصرف‌کننده کنسول را برای دیدن داده‌های موضوع اجرا کنیم (یا از کد مصرف‌کننده سفارشی برای پردازش آن استفاده کنیم):

```
> bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic connect-test --from-beginning
{"schema":{"type":"string","optional":false},"payload":"foo"}
{"schema":{"type":"string","optional":false},"payload":"bar"}
...
```

اتصال دهنده ها به پردازش داده ها ادامه می دهند، بنابراین ما می توانیم داده ها را به فایل اضافه کنیم و شاهد حرکت آن در خط لوله باشیم:

```
> echo Another line>> test.txt

```

باید این خط را در خروجی مصرف کننده کنسول و در فایل سینک مشاهده کنید.

مرحله 7: رویدادهای خود را با کافکا استریمز پردازش کنید
هنگامی که داده های شما به عنوان رویداد در کافکا ذخیره می شوند، می توانید داده ها را با کتابخانه مشتری Kafka Streams برای جاوا/اسکالا پردازش کنید. این به شما امکان می‌دهد تا برنامه‌ها و ریزسرویس‌های لحظه‌ای حیاتی را پیاده‌سازی کنید، جایی که داده‌های ورودی و/یا خروجی در موضوعات کافکا ذخیره می‌شوند. Kafka Streams سادگی نوشتن و استقرار برنامه‌های جاوا و اسکالا استاندارد در سمت کلاینت را با مزایای فناوری خوشه سمت سرور کافکا ترکیب می‌کند تا این برنامه‌ها را بسیار مقیاس‌پذیر، الاستیک، مقاوم در برابر خطا و توزیع کند. این کتابخانه دقیقاً یک بار پردازش، عملیات و تجمیع حالت، پنجره‌سازی، پیوستن، پردازش بر اساس زمان رویداد و موارد دیگر را پشتیبانی می‌کند.

برای اولین بار، نحوه پیاده سازی الگوریتم محبوب WordCount را در اینجا آورده ایم:

```
KStream<String, String> textLines = builder.stream("quickstart-events");

KTable<String, Long> wordCounts = textLines
            .flatMapValues(line -> Arrays.asList(line.toLowerCase().split(" ")))
            .groupBy((keyIgnored, word) -> word)
            .count();

wordCounts.toStream().to("output-topic", Produced.with(Serdes.String(), Serdes.Long()));
```

مرحله 8: محیط کافکا را خاتمه دهید
اکنون که به پایان شروع سریع رسیده‌اید، با خیال راحت محیط کافکا را خراب کنید—یا به بازی کردن ادامه دهید.

اگر قبلاً این کار را نکرده‌اید، با Ctrl-C مشتریان تولیدکننده و مصرف‌کننده را متوقف کنید.
کارگزار کافکا را با Ctrl-C متوقف کنید.
در نهایت، اگر بخش Kafka with ZooKeeper دنبال شد، سرور ZooKeeper را با Ctrl-C متوقف کنید.
اگر همچنین می‌خواهید داده‌های محیط کافکا محلی خود را حذف کنید، از جمله رویدادهایی که در طول مسیر ایجاد کرده‌اید، دستور را اجرا کنید:

```
$ rm -rf /tmp/kafka-logs /tmp/zookeeper /tmp/kraft-combined-logs

```

پس از طی این مراحل
شما شروع سریع آپاچی کافکا را با موفقیت به پایان رساندید.

برای کسب اطلاعات بیشتر مراحل زیر را پیشنهاد می کنیم:

مقدمه کوتاه را بخوانید تا با نحوه عملکرد کافکا در سطح بالا، مفاهیم اصلی آن و مقایسه آن با سایر فناوری‌ها آشنا شوید. برای درک بیشتر کافکا، به مستندات مراجعه کنید.
موارد استفاده را مرور کنید تا بدانید چگونه سایر کاربران در جامعه جهانی ما از کافکا ارزش می‌گیرند.
به یک گروه ملاقات محلی کافکا بپیوندید و گفتگوهای نشست کافکا، کنفرانس اصلی جامعه کافکا را تماشا کنید.

</h4>

</br>
</br>

<h2 dir='ltr'>
Producer API
</h2>

<h4>

Producer API به برنامه‌ها اجازه می‌دهد تا جریان‌هایی از داده‌ها را به موضوعاتی در خوشه کافکا ارسال کنند.
نمونه هایی که نحوه استفاده از سازنده را نشان می دهد در جاوادوک آورده شده است.

برای استفاده از تولید کننده، می توانید از وابستگی maven زیر استفاده کنید:

```
<dependency>
	<groupId>org.apache.kafka</groupId>
	<artifactId>kafka-clients</artifactId>
	<version>3.4.0</version>
</dependency>
```

</h4>
</br>
</br>

<h2 dir='ltr'>
Consumer API
</h2>

<h4>
Consumer API به برنامه‌ها اجازه می‌دهد تا جریان‌های داده‌ها را از موضوعات در خوشه کافکا بخوانند.
مثال هایی که نحوه استفاده از مصرف کننده را نشان می دهد در جاوادوک آورده شده است.

برای استفاده از مصرف کننده، می توانید از وابستگی maven زیر استفاده کنید:

```
<dependency>
	<groupId>org.apache.kafka</groupId>
	<artifactId>kafka-clients</artifactId>
	<version>3.4.0</version>
</dependency>
```

</h4>
</br>
</br>

<h2 dir='ltr'>
Streams API
</h2>

<h4>
Streams API اجازه می دهد تا جریان های داده را از موضوعات ورودی به موضوعات خروجی تبدیل کند.
نمونه هایی که نحوه استفاده از این کتابخانه را نشان می دهد در جاوادوک آورده شده است

اسناد اضافی در مورد استفاده از Streams API در اینجا موجود است.

برای استفاده از Kafka Streams می توانید از وابستگی maven زیر استفاده کنید:

```
<dependency>
	<groupId>org.apache.kafka</groupId>
	<artifactId>kafka-streams</artifactId>
	<version>3.4.0</version>
</dependency>
```

هنگام استفاده از Scala، می‌توانید به صورت اختیاری کتابخانه kafka-streams-scala را اضافه کنید. اسناد اضافی در مورد استفاده از Kafka Streams DSL برای Scala در راهنمای توسعه دهنده موجود است.

برای استفاده از Kafka Streams DSL for Scala for Scala 2.13 می توانید از وابستگی maven زیر استفاده کنید:

```
<dependency>
	<groupId>org.apache.kafka</groupId>
	<artifactId>kafka-streams-scala_2.13</artifactId>
	<version>3.4.0</version>
</dependency>
```

</h4>
</br>
</br>

<h2 dir="ltr">
Connect API
</h2>

<h4>
Connect API اجازه می دهد تا اتصال دهنده هایی را پیاده سازی کند که به طور مداوم از برخی از سیستم های داده منبع به کافکا کشیده می شوند یا از کافکا به برخی از سیستم های داده سینک فشار می آورند.
بسیاری از کاربران Connect نیازی به استفاده مستقیم از این API نخواهند داشت، اگرچه می‌توانند بدون نیاز به نوشتن کد از کانکتورهای از پیش ساخته شده استفاده کنند. اطلاعات اضافی در مورد استفاده از Connect در اینجا موجود است.

کسانی که می خواهند کانکتورهای سفارشی را پیاده سازی کنند می توانند javadoc را ببینند.

</h4>
</br>
</br>

<h2 dir="ltr">
Admin API
</h2>

<h4>
Admin API از مدیریت و بازرسی موضوعات، بروکرها، acls و سایر اشیاء کافکا پشتیبانی می کند.
برای استفاده از Admin API، وابستگی Maven زیر را اضافه کنید:

```
<dependency>
	<groupId>org.apache.kafka</groupId>
	<artifactId>kafka-clients</artifactId>
	<version>3.4.0</version>
</dependency>
```

</h4>
</br>
</br>

</div>



