<h2 align=right>‫فاصله در عبارات و دستورات:</h2>

<p align=right>‫از فاصله‌های نامربوط که در شرایط زیر صدق می‌کنند بپرهیزید:</p>

<p align=right>‫I. بدون هیچ واسطه در داخل پرانتز‌ها، آکولادها و کروشه‌ها:</p>

<pre><code>Yes:
    spam(ham[1], {eggs: 2})
No:
    spam( ham[ 1 ], { eggs: 2 } )
</code></pre>

<p align=right>‫II. بدون هیچ واسطه قبل از کاما، سمی‌کولن(semicolon) و کولن(colon):</p>

<pre><code>Yes:
    if x == 4: print(x, y); x, y = y, x
No:
    if x == 4 : print(x , y) ; x , y = y , x
</code></pre>

<p align=right>‫III. برخی اوقات کولن شبیه به یک عملگر دودویی رفتار می‌کنه پس باید ما هم باهاش مثل یه عملگر رفتار کنیم حداقل یه عملگر با اولویت پایین و اطراف اون فاصله بزاریم البته به غیر از زمان‌هایی که عملوند اون حذف شده باشه بطوریکه فاصله از سمت عملوند هم حذف می‌شه:</p>

<pre><code>Yes:
    ham[1:9], ham[1:9:3], ham[:9:3], ham[1::3], ham[1:9:]
    ham[lower:upper], ham[lower:upper:], ham[lower::step]
    ham[lower+offset : upper+offset]
    ham[: upper_fn(x) : step_fn(x)], ham[:: step_fn(x)]
    ham[lower + offset : upper + offset]
No:
    ham[lower + offset:upper + offset]
    ham[1: 9], ham[1 :9], ham[1:9 :3]
    ham[lower : : upper]
    ham[ : ]
</code></pre>

<p align=right>‫IV. بدون واسطه قبل از پرانتز باز برای مشخص کردن آرگومان‌های تابع هنگام فراخوانی:</p>

<pre><code>Yes:
    spam(1)
No:
    spam (1)
</code></pre>

<p align=right>‫V. بدون واسطه قبل از پرانتز باز برای شروع indexing:</p>

<pre><code>Yes:
    dct['key'] = lst[index]
No:
    dct ['key'] = lst [index]
</code></pre>

<p align=right>‫VI. بیش از یک فاصله اطراف تساوی انتساب (یا هر تساوی دیگر) به بهانه‌ی تراز دادن با بقیه:</p>

<pre><code>Yes:
    x = 1
    y = 2
    long_variable = 3
No:
    x             = 1
    y             = 2
    long_variable = 3
</code></pre>

<h3 align=right>‫ باقی توصیه‌ها:</h3>

<p align=right>‫I. این عملگر‌های باینری را همیشه با یک فاصله در اطراف آن‌ها محاصره کنید: انتساب ( = )، انتساب‌های تکمیلی (‪+=, -=‬ و …)، مقایسه‌ای‪( == , &lt; , > , != , &lt;> , &lt;= , >= , in , not in , is , is not )‬، بولی (and , or , not).</p>

<p align=right>‫II. اگر عملگر‌هایی با اولویت‌های متفاوت مورد استفاده قرار گیرند، فقط اطراف عملگر با اولویت کمتر فاصله قرار می‌دهیم البته این بیشتر به تشخیص و سلیقه‌ی شخصی شما بستگی دارد،‌ امّا، هیچ وقت بیشتر از یک فاصله استفاده نکنید و همیشه در هر دو طرف عملگر به یک میزان فاصله قرار دهید.</p>

<pre><code>Yes:
    i = i + 1
    submitted += 1
    x = x*2 – 1
    hypot2 = x*x + y*y
    c = (a+b) * (a-b)
No:
    i=i+1
    submitted +=1
    x = x * 2 – 1
    hypot2 = x * x + y * y
    c = (a + b) * (a - b)
</code></pre>

<p align=right>‫III. هنگام استفاده از = برای مقداری دهی اولیه به پارامتر یا مشخص کردن مقدار یک آرگومان اطراف آن از فاصله استفاده نمی‌کنیم.</p>

<pre><code>Yes:
    def complex(real, image=0.0):
        return magic(r=real, i=image)
No:
    def complex(real, image = 0.0):
        return magic(r = real, i = image)
</code></pre>

<p align=right>‫IV. استفاده  از جملات مرّکب (چندین جمله در یک خط) اصلاً توصیه نمی‌شه: </p>

<pre><code>Yes:
    if foo == 'blah':
        do_blah_thing()
    do_one()
    do_two()
    do_three()
Rather No:
    if foo == 'blah': do_blah_thing()
    do_one(); do_two(); do_three()
</code></pre>

<p align=right>‫V. زمانی که می‌توان ساختار‌های if/for/while را در یک قالب کوچک تک خطی نوشت هرگز آن‌ها را در چندین قالب ننویسید:</p>

<pre><code>Rather No:
    if foo == 'blah': do_blah_thing()
    for x in lst: total += x
    while t &lt; 10: t = delay()
Definitely No:
    if foo == 'blah': do_blah_thing()
    else: do_non_blah_thing()

    try: somthing()
    finally: cleanup()

    do_one(); do_two(); do_three(long, argument,
                                 list, like, this)

    if foo == 'blah': one(); two(); three()
</code></pre>

<p align=center><a href="https://github.com/vahit/pep8-per/blob/master/partv.md">بعدی</a> <a href="https://github.com/vahit/pep8-per/blob/master/partiii.md">قبلی</a></p>
<p align=right>