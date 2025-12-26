<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موقع الأسئلة الدينية | نور المعرفة</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700&display=swap">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Cairo', sans-serif;
        }
        
        :root {
            --primary-color: #2c786c;
            --secondary-color: #004445;
            --accent-color: #f8b400;
            --light-color: #faf5e4;
            --dark-color: #1a2c2a;
            --text-color: #333;
            --shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }
        
        body {
            background-color: #f9f9f9;
            color: var(--text-color);
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><path fill="%232c786c" opacity="0.03" d="M0,0 L100,0 L100,100 L0,100 Z M50,50 C65,45 75,35 80,20 C85,35 95,45 100,50 C95,55 85,65 80,80 C75,65 65,55 50,50 Z"/></svg>');
        }
        
        /* تصميم الهيدر */
        header {
            background: linear-gradient(135deg, var(--secondary-color) 0%, var(--primary-color) 100%);
            color: white;
            padding: 1rem 5%;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo i {
            font-size: 2rem;
            color: var(--accent-color);
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        .logo span {
            color: var(--accent-color);
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 1.5rem;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-weight: 600;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            transition: var(--transition);
        }
        
        nav a:hover, nav a.active {
            background-color: rgba(255, 255, 255, 0.2);
            color: var(--accent-color);
        }
        
        .auth-buttons {
            display: flex;
            gap: 1rem;
        }
        
        .auth-btn {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 0.6rem 1.2rem;
            border: none;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .facebook-btn {
            background-color: #3b5998;
            color: white;
        }
        
        .google-btn {
            background-color: white;
            color: #444;
        }
        
        .auth-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        /* قسم الذكر اليومي */
        .daily-reminder {
            background: linear-gradient(135deg, var(--light-color) 0%, #e8f4f1 100%);
            padding: 3rem 5%;
            text-align: center;
            margin: 2rem 5%;
            border-radius: 15px;
            box-shadow: var(--shadow);
            border-right: 8px solid var(--accent-color);
            position: relative;
            overflow: hidden;
        }
        
        .daily-reminder::before {
            content: "";
            font-family: "Font Awesome 6 Free";
            font-weight: 900;
            position: absolute;
            top: -30px;
            right: -30px;
            font-size: 15rem;
            color: rgba(44, 120, 108, 0.05);
            z-index: 0;
        }
        
        .reminder-title {
            color: var(--secondary-color);
            margin-bottom: 1.5rem;
            font-size: 1.8rem;
            position: relative;
            z-index: 1;
        }
        
        .reminder-text {
            font-size: 1.8rem;
            color: var(--primary-color);
            margin-bottom: 1.5rem;
            font-weight: 600;
            position: relative;
            z-index: 1;
            line-height: 1.8;
        }
        
        .reminder-source {
            color: #666;
            font-style: italic;
            position: relative;
            z-index: 1;
        }
        
        /* الأقسام الرئيسية */
        .main-content {
            padding: 2rem 5%;
            flex: 1;
        }
        
        .sections-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }
        
        .section-card {
            background-color: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            height: 100%;
        }
        
        .section-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
        
        .card-header {
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 1.5rem;
            text-align: center;
        }
        
        .card-header i {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .card-header h3 {
            font-size: 1.5rem;
        }
        
        .card-body {
            padding: 1.5rem;
        }
        
        /* قسم الأسئلة */
        .question-item {
            padding: 1rem;
            border-bottom: 1px solid #eee;
            transition: var(--transition);
        }
        
        .question-item:hover {
            background-color: #f9f9f9;
        }
        
        .question-title {
            font-weight: 600;
            color: var(--secondary-color);
            margin-bottom: 0.5rem;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .question-title i {
            color: var(--primary-color);
        }
        
        /* قسم مواقيت الصلاة */
        .prayer-times {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }
        
        .prayer-time {
            display: flex;
            justify-content: space-between;
            padding: 1rem;
            background-color: #f5f9f8;
            border-radius: 10px;
            border-right: 4px solid var(--primary-color);
        }
        
        .prayer-name {
            font-weight: 600;
            color: var(--secondary-color);
        }
        
        .prayer-time-value {
            font-weight: 700;
            color: var(--primary-color);
            font-size: 1.1rem;
        }
        
        .current-prayer {
            background-color: #e8f4f1;
            border-right-color: var(--accent-color);
        }
        
        /* قسم اتجاه القبلة */
        .qibla-direction {
            text-align: center;
            padding: 2rem 1rem;
        }
        
        .qibla-compass {
            width: 200px;
            height: 200px;
            margin: 1.5rem auto;
            position: relative;
            background: conic-gradient(from 0deg, #f8b400 0%, #f8b400 50%, #e8f4f1 50%, #e8f4f1 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        }
        
        .compass-arrow {
            width: 40px;
            height: 40px;
            background-color: var(--secondary-color);
            clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
            transform: rotate(45deg);
        }
        
        .qibla-text {
            margin-top: 1.5rem;
            font-size: 1.2rem;
            color: var(--primary-color);
            font-weight: 600;
        }
        
        .location-input {
            margin-top: 1.5rem;
            display: flex;
            gap: 10px;
        }
        
        .location-input input {
            flex: 1;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
        }
        
        .location-input button {
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 8px;
            padding: 0.8rem 1.5rem;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .location-input button:hover {
            background-color: var(--secondary-color);
        }
        
        /* الفوتر */
        footer {
            background: linear-gradient(135deg, var(--dark-color) 0%, var(--secondary-color) 100%);
            color: white;
            padding: 3rem 5% 2rem;
            margin-top: 3rem;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }
        
        .developer-info {
            margin-bottom: 2rem;
        }
        
        .developer-info h3 {
            font-size: 1.8rem;
            margin-bottom: 0.5rem;
            color: var(--accent-color);
        }
        
        .developer-info p {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
        }
        
        .whatsapp-contact {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 1rem;
            margin: 2rem 0;
        }
        
        .whatsapp-number {
            font-size: 1.5rem;
            font-weight: 700;
            color: #25D366;
            direction: ltr;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .whatsapp-icon {
            font-size: 3rem;
            color: #25D366;
            animation: pulse 2s infinite;
            position: relative;
        }
        
        .whatsapp-icon::after {
            content: "";
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background-color: #25D366;
            opacity: 0.3;
            animation: ripple 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        @keyframes ripple {
            0% { transform: scale(1); opacity: 0.3; }
            100% { transform: scale(1.5); opacity: 0; }
        }
        
        .copyright {
            margin-top: 2rem;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            width: 100%;
            color: #aaa;
        }
        
        /* تصميم متجاوب */
        @media (max-width: 992px) {
            .header-container {
                flex-direction: column;
                gap: 1rem;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .sections-container {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 768px) {
            .daily-reminder {
                margin: 1rem;
                padding: 2rem 1rem;
            }
            
            .reminder-text {
                font-size: 1.5rem;
            }
            
            .whatsapp-number {
                font-size: 1.2rem;
            }
        }
        
        @media (max-width: 576px) {
            .auth-buttons {
                flex-direction: column;
                width: 100%;
            }
            
            .auth-btn {
                justify-content: center;
            }
            
            .location-input {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- الهيدر -->
    <header>
        <div class="header-container">
            <div class="logo">
                <i class="fas fa-mosque"></i>
                <h1>نور <span>المعرفة</span></h1>
            </div>
            
            <nav>
                <ul>
                    <li><a href="#" class="active">الرئيسية</a></li>
                    <li><a href="#questions">الأسئلة الدينية</a></li>
                    <li><a href="#prayer">مواقيت الصلاة</a></li>
                    <li><a href="#qibla">اتجاه القبلة</a></li>
                </ul>
            </nav>
            
            <div class="auth-buttons">
                <button class="auth-btn facebook-btn">
                    <i class="fab fa-facebook-f"></i>
                    تسجيل الدخول بفيسبوك
                </button>
                <button class="auth-btn google-btn">
                    <i class="fab fa-google"></i>
                    تسجيل الدخول بجوجل
                </button>
            </div>
        </div>
    </header>
    
    <!-- الذكر اليومي -->
    <section class="daily-reminder">
        <h2 class="reminder-title">ذكر اليوم</h2>
        <p class="reminder-text">اللهم إني أسألك علماً نافعاً، ورزقاً طيباً، وعملاً متقبلاً</p>
        <p class="reminder-source">دعاء الرسول صلى الله عليه وسلم</p>
    </section>
    
    <!-- الأقسام الرئيسية -->
    <main class="main-content">
        <div class="sections-container">
            <!-- قسم الأسئلة الدينية -->
            <section class="section-card" id="questions">
                <div class="card-header">
                    <i class="fas fa-question-circle"></i>
                    <h3>الأسئلة الدينية</h3>
                </div>
                <div class="card-body">
                    <div class="question-item">
                        <div class="question-title">
                            ما هي أركان الإسلام؟
                            <i class="fas fa-chevron-down"></i>
                        </div>
                    </div>
                    <div class="question-item">
                        <div class="question-title">
                            ما هي شروط الصلاة؟
                            <i class="fas fa-chevron-down"></i>
                        </div>
                    </div>
                    <div class="question-item">
                        <div class="question-title">
                            ما هو حكم الصلاة في الإسلام؟
                            <i class="fas fa-chevron-down"></i>
                        </div>
                    </div>
                    <div class="question-item">
                        <div class="question-title">
                            كيف تكون التوبة الصادقة؟
                            <i class="fas fa-chevron-down"></i>
                        </div>
                    </div>
                    <div class="question-item">
                        <div class="question-title">
                            ما هي فضائل قراءة القرآن؟
                            <i class="fas fa-chevron-down"></i>
                        </div>
                    </div>
                </div>
            </section>
            
            <!-- قسم مواقيت الصلاة -->
            <section class="section-card" id="prayer">
                <div class="card-header">
                    <i class="fas fa-clock"></i>
                    <h3>مواقيت الصلاة</h3>
                </div>
                <div class="card-body">
                    <div class="prayer-times">
                        <div class="prayer-time">
                            <span class="prayer-name">الفجر</span>
                            <span class="prayer-time-value">4:30 ص</span>
                        </div>
                        <div class="prayer-time">
                            <span class="prayer-name">الشروق</span>
                            <span class="prayer-time-value">5:45 ص</span>
                        </div>
                        <div class="prayer-time current-prayer">
                            <span class="prayer-name">الظهر</span>
                            <span class="prayer-time-value">12:15 م</span>
                        </div>
                        <div class="prayer-time">
                            <span class="prayer-name">العصر</span>
                            <span class="prayer-time-value">3:45 م</span>
                        </div>
                        <div class="prayer-time">
                            <span class="prayer-name">المغرب</span>
                            <span class="prayer-time-value">6:30 م</span>
                        </div>
                        <div class="prayer-time">
                            <span class="prayer-name">العشاء</span>
                            <span class="prayer-time-value">8:00 م</span>
                        </div>
                    </div>
                </div>
            </section>
            
            <!-- قسم اتجاه القبلة -->
            <section class="section-card" id="qibla">
                <div class="card-header">
                    <i class="fas fa-compass"></i>
                    <h3>اتجاه القبلة</h3>
                </div>
                <div class="card-body">
                    <div class="qibla-direction">
                        <div class="qibla-compass">
                            <div class="compass-arrow"></div>
                        </div>
                        <p class="qibla-text">اتجاه القبلة: جنوب شرق (SE)</p>
                        <p>لحساب اتجاه القبلة بدقة لمكانك، أدخل موقعك:</p>
                        <div class="location-input">
                            <input type="text" id="location" placeholder="أدخل اسم مدينتك أو بلدك">
                            <button id="find-qibla">تحديد القبلة</button>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </main>
    
    <!-- الفوتر -->
    <footer>
        <div class="footer-content">
            <div class="developer-info">
                <h3>منشئ و مبرمج الموقع</h3>
                <p>المهندس: عامر عمران</p>
                <p>مطور ويب محترف متخصص في التصميم الديني</p>
            </div>
            
            <div class="whatsapp-contact">
                <div class="whatsapp-icon">
                    <i class="fab fa-whatsapp"></i>
                </div>
                <div class="whatsapp-number">
                    <i class="fas fa-phone"></i>
                    07506619617
                </div>
                <p>للتواصل عبر واتساب للاستفسارات أو تطوير مواقع</p>
            </div>
            
            <div class="copyright">
                <p>جميع الحقوق محفوظة &copy; 2023 موقع نور المعرفة</p>
                <p>تصميم وتطوير: عامر عمران</p>
            </div>
        </div>
    </footer>
    
    <script>
        // بيانات الذكر اليومي
        const dailyReminders = [
            {text: "اللهم إني أسألك علماً نافعاً، ورزقاً طيباً، وعملاً متقبلاً", source: "دعاء الرسول صلى الله عليه وسلم"},
            {text: "من قال سبحان الله وبحمده، غرست له نخلة في الجنة", source: "حديث شريف"},
            {text: "اللهم أعني على ذكرك وشكرك وحسن عبادتك", source: "دعاء مأثور"},
            {text: "رَبَّنَا آتِنَا فِي الدُّنْيَا حَسَنَةً وَفِي الآخِرَةِ حَسَنَةً وَقِنَا عَذَابَ النَّارِ", source: "سورة البقرة - الآية 201"},
            {text: "اللهم أصلح لي ديني الذي هو عصمة أمري، وأصلح لي دنياي التي فيها معاشي", source: "دعاء مأثور"},
            {text: "حسبي الله لا إله إلا هو، عليه توكلت وهو رب العرش العظيم", source: "سورة التوبة - الآية 129"}
        ];
        
        // تغيير الذكر يومياً (بناء على تاريخ اليوم)
        document.addEventListener('DOMContentLoaded', function() {
            // اختيار ذكر بناء على تاريخ اليوم
            const today = new Date().getDate();
            const reminderIndex = today % dailyReminders.length;
            const reminder = dailyReminders[reminderIndex];
            
            document.querySelector('.reminder-text').textContent = reminder.text;
            document.querySelector('.reminder-source').textContent = reminder.source;
            
            // إضافة تأثير للأسئلة عند النقر
            const questionTitles = document.querySelectorAll('.question-title');
            questionTitles.forEach(title => {
                title.addEventListener('click', function() {
                    const answer = this.nextElementSibling;
                    if (answer && answer.classList.contains('answer')) {
                        answer.style.display = answer.style.display === 'block' ? 'none' : 'block';
                    } else {
                        // إنشاء إجابة إذا لم تكن موجودة
                        const answerDiv = document.createElement('div');
                        answerDiv.className = 'answer';
                        answerDiv.innerHTML = '<p>هذا نموذج للإجابة. في الموقع الحقيقي ستكون هنا إجابات مفصلة على الأسئلة الدينية من مصادر موثوقة.</p>';
                        answerDiv.style.padding = '1rem';
                        answerDiv.style.backgroundColor = '#f9f9f9';
                        answerDiv.style.borderTop = '1px solid #eee';
                        answerDiv.style.marginTop = '0.5rem';
                        
                        this.parentNode.insertBefore(answerDiv, this.nextSibling);
                    }
                    
                    // تغيير الأيقونة
                    const icon = this.querySelector('i');
                    if (icon.classList.contains('fa-chevron-down')) {
                        icon.classList.remove('fa-chevron-down');
                        icon.classList.add('fa-chevron-up');
                    } else {
                        icon.classList.remove('fa-chevron-up');
                        icon.classList.add('fa-chevron-down');
                    }
                });
            });
            
            // محاكاة زر تحديد القبلة
            document.getElementById('find-qibla').addEventListener('click', function() {
                const location = document.getElementById('location').value;
                if (location.trim() === '') {
                    alert('الرجاء إدخال موقعك للحصول على اتجاه القبلة بدقة');
                } else {
                    alert(`سيتم تحديد اتجاه القبلة لموقع: ${location}\n\nفي الموقع الحقيقي، سيتم هنا الاتصال بخدمة تحديد الموقع الجغرافي واتجاه القبلة.`);
                }
            });
            
            // محاكاة تسجيل الدخول
            const authButtons = document.querySelectorAll('.auth-btn');
            authButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const provider = this.classList.contains('facebook-btn') ? 'فيسبوك' : 'جوجل';
                    alert(`سيتم الآن توجيهك لصفحة تسجيل الدخول عبر ${provider}.\n\nفي الموقع الحقيقي، سيتم هنا تنفيذ عملية OAuth الكاملة.`);
                });
            });
            
            // تحديث وقت الصلاة الحالي
            function updateCurrentPrayer() {
                const now = new Date();
                const currentTime = now.getHours() * 60 + now.getMinutes(); // الوقت الحالي بالدقائق
                
                // أوقات الصلاة بالدقائق (توقيتات افتراضية)
                const prayerTimes = {
                    fajr: 4 * 60 + 30,    // 4:30
                    sunrise: 5 * 60 + 45, // 5:45
                    dhuhr: 12 * 60 + 15,  // 12:15
                    asr: 15 * 60 + 45,    // 15:45
                    maghrib: 18 * 60 + 30, // 18:30
                    isha: 20 * 60 + 0     // 20:00
                };
                
                // تحديد الصلاة الحالية
                let currentPrayer = null;
                const prayers = document.querySelectorAll('.prayer-time');
                prayers.forEach(prayer => prayer.classList.remove('current-prayer'));
                
                if (currentTime >= prayerTimes.isha || currentTime < prayerTimes.fajr) {
                    currentPrayer = prayers[5]; // العشاء
                } else if (currentTime >= prayerTimes.maghrib) {
                    currentPrayer = prayers[4]; // المغرب
                } else if (currentTime >= prayerTimes.asr) {
                    currentPrayer = prayers[3]; // العصر
                } else if (currentTime >= prayerTimes.dhuhr) {
                    currentPrayer = prayers[2]; // الظهر
                } else if (currentTime >= prayerTimes.sunrise) {
                    currentPrayer = prayers[1]; // الشروق
                } else if (currentTime >= prayerTimes.fajr) {
                    currentPrayer = prayers[0]; // الفجر
                }
                
                if (currentPrayer) {
                    currentPrayer.classList.add('current-prayer');
                }
            }
            
            // تحديث وقت الصلاة الحالي كل دقيقة
            updateCurrentPrayer();
            setInterval(updateCurrentPrayer, 60000);
            
            // تأثير تحريك البوصلة عند التمرير
            window.addEventListener('scroll', function() {
                const compass = document.querySelector('.qibla-compass');
                const scrollPosition = window.scrollY;
                compass.style.transform = `rotate(${scrollPosition % 360}deg)`;
            });
        });
    </script>
</body>
</html>
