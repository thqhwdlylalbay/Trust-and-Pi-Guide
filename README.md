<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مشروع ثقة ودليل الباي (Trust & Pi Guide)</title>
    <style>
        :root {
            --primary-color: #673ab7;
            --secondary-color: #512da8;
            --bg-color: #f4f7f6;
            --text-color: #333;
        }
        body { 
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; 
            background-color: var(--bg-color); 
            color: var(--text-color);
            margin: 0; padding: 20px;
            line-height: 1.6;
        }
        .container { max-width: 800px; margin: auto; }
        
        /* تصميم الهيدر */
        header { text-align: center; padding: 20px; background: white; border-radius: 15px; box-shadow: 0 4px 15px rgba(0,0,0,0.05); margin-bottom: 20px; }
        header h1 { color: var(--primary-color); margin: 0; }
        
        /* تصميم حاسبة الاستيكينج */
        .staking-section { 
            background: white; padding: 25px; border-radius: 15px; 
            box-shadow: 0 10px 25px rgba(0,0,0,0.1); margin-bottom: 30px;
            border-top: 5px solid var(--primary-color);
        }
        .staking-section h2 { text-align: center; color: var(--primary-color); }
        input { 
            width: 100%; padding: 12px; margin: 10px 0; 
            border: 1px solid #ddd; border-radius: 8px; 
            box-sizing: border-box; font-size: 16px; 
        }
        button { 
            width: 100%; background-color: var(--primary-color); color: white; 
            border: none; padding: 15px; border-radius: 8px; 
            font-size: 18px; cursor: pointer; transition: 0.3s; 
        }
        button:hover { background-color: var(--secondary-color); }
        #result { margin-top: 20px; text-align: center; font-weight: bold; font-size: 1.1rem; color: #2e7d32; }

        /* تصميم دليل التجار */
        .merchants-section { background: white; padding: 20px; border-radius: 15px; box-shadow: 0 4px 15px rgba(0,0,0,0.05); }
        .merchant-card { 
            background: #fafafa; border-right: 4px solid var(--primary-color); 
            padding: 15px; margin-bottom: 15px; border-radius: 5px;
        }
        .merchant-card h3 { margin-top: 0; color: #444; }
        .status { color: #d32f2f; font-weight: bold; font-size: 0.9rem; }
        
        .contact-btn {
            display: inline-block; background: #e8f5e9; color: #2e7d32;
            padding: 10px 20px; border-radius: 20px; text-decoration: none;
            margin-top: 20px; font-weight: bold;
        }
    </style>
</head>
<body>

<div class="container">
    <header>
        <h1>🛡️ ثقة ودليل الباي</h1>
        <p>الدليل الرسمي والفعلي لرواد Pi Network</p>
    </header>

    <section class="staking-section">
        <h2>🧮 حاسبة الأرباح (Staking)</h2>
        <input type="number" id="piAmount" placeholder="أدخل كمية عملات Pi">
        <input type="number" id="lockRate" placeholder="نسبة الفائدة السنوية (%)">
        <input type="number" id="lockPeriod" placeholder="مدة الحجز (بالسنوات)">
        <button onclick="calculatePi()">احسب المكافأة الآن</button>
        <div id="result"></div>
    </section>

    <section class="merchants-section">
        <h2>🏪 دليل التجار المعتمدين</h2>
        <p>نحن نبحث عن الأفضل لتوثيقه وتقديمه لكم:</p>

        <div class="merchant-card">
            <h3>📱 متجر الثقة للموبايلات</h3>
            <p>القاهرة - صيانة وبيع | <b>نسبة القبول: 50% Pi</b></p>
        </div>

        <div class="merchant-card">
            <h3>💻 الفارس لشحن الألعاب</h3>
            <p>أونلاين - خدمات رقمية | <b>نسبة القبول: 100% Pi</b></p>
        </div>

        <div class="merchant-card">
            <h3>🛒 سوبر ماركت الأمان</h3>
            <p>الإسكندرية - سلع استهلاكية | <span class="status">جاري تدقيق العنوان..</span></p>
        </div>

        <div style="text-align: center;">
            <a href="mailto:thqhwdlylalbay@gmail.com?subject=طلب%20توثيق%20تاجر%20جديد" class="contact-btn">
                📩 هل تريد إضافة نشاطك التجاري؟ تواصل معنا
            </a>
        </div>
    </section>
</div>

<script>
    function calculatePi() {
        const amount = parseFloat(document.getElementById('piAmount').value);
        const rate = parseFloat(document.getElementById('lockRate').value) / 100;
        const years = parseFloat(document.getElementById('lockPeriod').value);

        if (isNaN(amount) || isNaN(rate) || isNaN(years)) {
            document.getElementById('result').innerText = "⚠️ يرجى إدخال أرقام صحيحة";
            return;
        }

        const reward = amount * rate * years;
        const total = amount + reward;
        document.getElementById('result').innerHTML = `
            ✅ المكافأة المتوقعة: ${reward.toFixed(2)} Pi<br>
            💰 الإجمالي بعد الحجز: ${total.toFixed(2)} Pi
        `;
    }
</script>

</body>
</html>
