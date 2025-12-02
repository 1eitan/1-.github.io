<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- שיפור SEO: כותרת מפורטת יותר -->
    <title>ישיבת אש קודש לצעירים באר שבע - לימוד תורה ובגרויות</title>
    
    <!-- --- תגיות SEO (Meta Tags) --- -->
    <meta name="description" content="אתר ישיבת אש קודש לצעירים בבאר שבע. לימוד תורה בעיון, סדרי חסידות ומחשבת ישראל, אירועים ועדכונים שוטפים. הצטרפו לחזון שלנו!">
    <meta name="keywords" content="ישיבת אש קודש, באר שבע, תורה, לימוד תורה, חסידות, גמרא, מדרשה, ישיבות לצעירים, תרומות, רבנים, פנימייה, בגרויות, לימודי תיכון">
    <!-- --------------------------------- -->

    <!-- טעינת Tailwind CSS דרך CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Heebo:wght@100..900&display=swap');
        
        :root {
            --color-primary: #1F3A60; /* Deep Indigo */
            --color-secondary: #fcd34d; /* Gold/Yellow */
            --color-background: #f9fafb; /* Light Gray */
            --color-accent: #EF4444; /* Red for emphasis / Live Chat */
        }
        
        /* הוספת גלילה חלקה */
        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Heebo', sans-serif;
            background-color: var(--color-background);
            color: #1f2937; /* Dark text (ניגודיות טובה) */
        }
        
        /* --- שיפורי פס ניווט (העדכון המרכזי) --- */
        
        /* הגובה הכללי של פס הניווט בדסקטופ - הופחת ל-60px */
        header .container {
            height: 60px; /* הופחת מ-70px */
        }

        /* סגנון הקישורים הרגילים בדסקטופ - הופחתו ריווחי ה-padding */
        nav a:not(.btn-primary) {
            position: relative;
            /* הופחת ריווח אנכי מ-0.75rem ל-0.5rem */
            padding-top: 0.5rem; 
            padding-bottom: 0.5rem; 
            display: flex; /* כדי להבטיח יישור אנכי */
            align-items: center;
        }

        /* הדגשה של הקישור הפעיל בתפריט */
        nav a.active {
            color: var(--color-primary) !important; 
            font-weight: 900 !important; /* אקסטרה בולט */
            border-bottom: 4px solid var(--color-secondary); /* קו תחתון עבה יותר בצבע זהב */
            padding-bottom: 4px !important; /* ריווח נמוך יותר כדי שלא יזלוג */
            border-radius: 0; 
            /* מגדיל מעט את הקישור הפעיל למראה חזק יותר בדסקטופ */
            font-size: 1.25rem; 
        }

        /* אפקט מעבר חלק על הקישורים (קו תחתון בריחוף) */
        #desktop-nav a:not(.btn-primary)::after {
            content: '';
            position: absolute;
            right: 0; 
            bottom: 0;
            width: 0%;
            height: 3px;
            background-color: var(--color-secondary);
            transition: width 0.3s ease-out;
        }
        #desktop-nav a:not(.btn-primary):hover:not(.active)::after {
            width: 100%;
        }
        /* -------------------------------------- */


        .btn-primary {
            background-color: var(--color-secondary);
            color: var(--color-primary);
            transition: all 0.3s;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
        }
        .btn-primary:hover {
            background-color: #f59e0b; 
            transform: translateY(-2px); 
        }

        .hero-section {
            background-color: var(--color-primary); 
            /* טעינה עצלה לתמונת רקע קונספטואלית */
            background-image: 
                linear-gradient(to bottom, rgba(31, 58, 96, 0.4), rgba(31, 58, 96, 0.6)),
                url("https://placehold.co/1200x800/1F3A60/fcd34d?text=Ash+Kodesh+Yeshiva+Be'er+Sheva"); 
            
            background-size: cover;
            background-position: center;
            background-attachment: fixed; 
        }

        /* שיפור רספונסיביות מתקדם (UX 1.ב) */
        @media (max-width: 480px) {
            .hero-section h1 {
                font-size: 2.5rem !important; 
            }
            .hero-section p {
                font-size: 1.25rem !important; 
            }
        }

        /* כפתור צ'אט צף (5.א) */
        #live-chat-btn {
            position: fixed;
            bottom: 1.5rem;
            left: 1.5rem; 
            z-index: 50;
            background-color: var(--color-accent); 
            color: white;
            transition: all 0.3s;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        #live-chat-btn:hover {
            background-color: #DC2626;
            transform: scale(1.05);
        }

        /* טאבים לסדרים - שיפור UX 1.ג */
        .seder-tab.active {
            background-color: var(--color-primary);
            color: var(--color-secondary);
        }

        /* סגנון מודל הודעה */
        #message-modal {
            transition: opacity 0.3s ease-in-out;
            opacity: 0;
            pointer-events: none;
        }
        #message-modal.active {
            opacity: 1;
            pointer-events: auto;
        }

        /* סגנון קטע עדויות - חדש */
        .testimonial-card {
            background: linear-gradient(135deg, #e0f2fe, #dbeafe); /* Light Blue Gradient */
            border-top: 5px solid var(--color-secondary);
        }

    </style>
</head>
<body class="antialiased">

    <!-- נגישות: קישורי דילוג (Skip Links) - 3.ג -->
    <a href="#main-content" class="sr-only focus:not-sr-only fixed top-0 left-1/2 -translate-x-1/2 bg-yellow-400 text-blue-900 p-3 font-bold z-[1000] rounded-b-lg transition duration-300" role="link">
        דלג לתוכן הראשי
    </a>
    <a href="#donate" class="sr-only focus:not-sr-only fixed top-12 left-1/2 -translate-x-1/2 bg-blue-900 text-yellow-400 p-3 font-bold z-[1000] rounded-b-lg transition duration-300" role="link">
        מעבר מהיר לתרומה
    </a>

    <!-- 1. פס ניווט (NavBar) -->
    <!-- שינוי גובה ה-container ל-h-[60px] דרך ה-CSS -->
    <header class="sticky top-0 z-50 bg-white shadow-xl border-t-4 border-blue-900">
        <!-- שינוי גובה ל-60px נעשה בתוך ה-CSS -->
        <div class="container mx-auto px-4 py-3 flex justify-between items-center">
            <!-- לוגו / שם הישיבה - עדכון: הבלטה ויזואלית -->
            <a href="#home" class="nav-link flex items-center space-x-2 space-x-reverse py-1" aria-label="ישיבת אש קודש - דף הבית" data-target="home">
                <span class="text-3xl md:text-4xl font-black text-blue-900 tracking-wider">
                    אש <span class="text-yellow-500">קודש</span>
                </span>
            </a>
            
            <!-- קישורי ניווט רגילים (למסכים גדולים) - עדכון: font-bold ו-align-items-center -->
            <nav id="desktop-nav" class="hidden md:flex space-x-8 space-x-reverse text-xl font-bold h-full items-center">
                <!-- הסרנו את h-full מהקישורים הפנימיים והקטנו את הריווח האנכי ב-CSS -->
                <a href="#about" class="nav-link text-gray-800 hover:text-blue-900 transition duration-300 px-3" data-target="about">על הישיבה</a>
                <a href="#testimonials" class="nav-link text-gray-800 hover:text-blue-900 transition duration-300 px-3" data-target="testimonials">בוגרים ותורמים</a>
                <a href="#updates" class="nav-link text-gray-800 hover:text-blue-900 transition duration-300 px-3" data-target="updates">עדכונים</a>
                <a href="#rabbis" class="nav-link text-gray-800 hover:text-blue-900 transition duration-300 px-3" data-target="rabbis">ראש הישיבה</a>
                <a href="#sedarim" class="nav-link text-gray-800 hover:text-blue-900 transition duration-300 px-3" data-target="sedarim">סדרים וזמנים</a>
                <a href="#contact" class="nav-link text-gray-800 hover:text-blue-900 transition duration-300 px-3" data-target="contact">צור קשר</a>
                <!-- כפתור תרומה - הוזז למעלה ע"י align-items-center ב-nav -->
                <a href="#donate" class="btn-primary py-2 px-4 ml-4 rounded-full font-extrabold nav-link text-base" data-target="donate" role="button">תרומה</a>
            </nav>
            
            <!-- כפתור המבורגר למובייל -->
            <button id="mobile-menu-button" class="md:hidden text-gray-800 hover:text-blue-900 transition duration-300 p-2 rounded-md focus:outline-none" aria-label="תפריט ניווט" aria-expanded="false">
                <!-- אייקון המבורגר -->
                <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="4" x2="20" y1="12" y2="12"/><line x1="4" x2="20" y1="6" y2="6"/><line x1="4" x2="20" y1="18" y2="18"/></svg>
            </button>
        </div>
        <!-- תפריט מובייל נשלף -->
        <div id="mobile-menu" class="hidden md:hidden bg-gray-50 border-t border-gray-200">
            <div class="px-2 pt-2 pb-3 space-y-1 text-center">
                <a href="#about" class="mobile-nav-link block py-2 px-3 text-lg font-bold text-gray-700 hover:bg-blue-100 rounded-lg" data-target="about">על הישיבה</a>
                <a href="#testimonials" class="mobile-nav-link block py-2 px-3 text-lg font-bold text-gray-700 hover:bg-blue-100 rounded-lg" data-target="testimonials">בוגרים ותורמים</a>
                <a href="#updates" class="mobile-nav-link block py-2 px-3 text-lg font-bold text-gray-700 hover:bg-blue-100 rounded-lg" data-target="updates">עדכונים</a>
                <a href="#rabbis" class="mobile-nav-link block py-2 px-3 text-lg font-bold text-gray-700 hover:bg-blue-100 rounded-lg" data-target="rabbis">ראש הישיבה</a>
                <a href="#sedarim" class="mobile-nav-link block py-2 px-3 text-lg font-bold text-gray-700 hover:bg-blue-100 rounded-lg" data-target="sedarim">סדרים וזמנים</a>
                <a href="#contact" class="mobile-nav-link block py-2 px-3 text-lg font-bold text-gray-700 hover:bg-blue-100 rounded-lg" data-target="contact">צור קשר</a>
                <a href="#donate" class="mobile-nav-link block py-2 px-3 text-lg font-extrabold text-blue-900 bg-yellow-400 hover:bg-yellow-500 rounded-lg mt-2" data-target="donate" role="button">תרומה</a>
            </div>
        </div>
    </header>

    <div id="main-content" tabindex="-1"> 
        <!-- 2. קטע ראשי (Hero Section) -->
        <section id="home" class="hero-section text-white text-center rounded-b-xl shadow-xl min-h-screen flex items-center justify-center">
            <div class="container mx-auto px-4 py-20 md:py-32">
                <!-- שיפור SEO: כותרת H1 ברורה -->
                <h1 class="text-5xl md:text-7xl font-extrabold mb-4 leading-tight" id="main-heading">
                    ישיבת אש קודש
                </h1>
                <!-- ****** שינוי: הבלטת בגרויות ****** -->
                <h2 class="text-2xl md:text-3xl font-light mb-8 text-yellow-400">
                    "וְאֵשׁ דָּת לָמוֹ" - ישיבה לצעירים המשלבת עומק תורני, לימודי תיכון והכנה מלאה לבגרויות
                </h2>
                <a href="#about" class="btn-primary py-3 px-8 text-xl rounded-full font-bold inline-block hover:scale-105" role="button">
                    קראו עוד על החזון שלנו
                </a>
            </div>
        </section>

        <!-- 3. אודות הישיבה (About Section) -->
        <section id="about" class="py-16 md:py-24">
            <div class="container mx-auto px-4 max-w-4xl">
                <h2 class="text-4xl font-bold text-center mb-10 border-b-4 border-yellow-400 inline-block pb-1 text-blue-900">
                    על הישיבה: חזון ודרך
                </h2>
                <div class="space-y-6 text-lg text-gray-700 leading-relaxed">
                    <p>
                        ישיבת "אש קודש לצעירים" הוקמה בבאר שבע מתוך חזון לחבר עומק תורני בלתי מתפשר עם עבודת ה' חיה ונושמת. אנו מאמינים כי התורה היא 'אש' הבוערת בלב כל יהודי ומכוונים את תלמידינו לצמיחה אישית ורוחנית מתוך שמחה ואחריות.
                    </p>
                    <p>
                        <h3 class="text-2xl font-bold text-blue-900 mt-6 mb-3">לימוד תורה בעיון וסדרי חסידות</h3>
                        הישיבה שמה דגש מיוחד על לימוד גמרא בעיון, לצד שיעורים קבועים בחסידות, מחשבת ישראל והלכה למעשה. מטרתנו היא להכשיר תלמידים שהם תלמידי חכמים, אך גם מנהיגים ואנשי מעשה, הפועלים להאיר את הכלל כולו באור התורה.
                        <!-- קישור פנימי - SEO 2.א -->
                        <span class="font-semibold text-yellow-600 hover:underline cursor-pointer">
                            לפרטים על זמני הלימוד, עברו לקטע <a href="#sedarim" title="מעבר לסדרי הלימוד היומיים">סדרים וזמנים</a>.
                        </span>
                    </p>
                    
                    <!-- ****** שינוי: סעיף פנימייה ולימודי תיכון מפורט ****** -->
                    <div class="bg-blue-50 border-r-4 border-blue-500 p-4 rounded-lg shadow-inner">
                        <h4 class="text-xl font-bold text-blue-800 mb-2">לימודי תיכון והצלחה בבגרויות</h4>
                        <p>
                            הישיבה מפעילה פנימייה מלאה ומסגרת לימודים תיכונית איכותית, המאפשרת לתלמידים לשלב לימוד תורה מלא עם **השלמת תעודת בגרות מלאה**. אנו רואים בלימודים הכלליים חלק בלתי נפרד מחינוך תלמיד חכם ומנהיג. המסלול מותאם אישית לכל תלמיד, ומכוון להצלחה מיטבית בכל מקצועות הבגרות, כולל מתמטיקה ואנגלית ברמה גבוהה. הצלחת התלמידים בבחינות היא יעד מרכזי שלנו, והצוות הפדגוגי מלווה כל תלמיד באופן צמוד ואישי.
                        </p>
                        <p class="mt-2 font-semibold text-blue-900">
                           תנאי הקבלה כוללים ראיון אישי ובחינה ברמה תורנית בסיסית ורצון עז לעבודת ה'.
                        </p>
                    </div>

                    <div class="bg-blue-50 border-r-4 border-blue-500 p-4 rounded-lg shadow-inner">
                        <p class="font-semibold text-blue-800">
                            החזון שלנו: תורה המחוברת לחיים, אמונה המפיחה רוח.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 3.5. עדויות בוגרים ותורמים (Testimonials Section) - חדש (סעיף 2) -->
        <section id="testimonials" class="py-16 md:py-24 bg-gray-200 border-t border-b">
            <div class="container mx-auto px-4 max-w-6xl">
                <h2 class="text-4xl font-bold text-center mb-12 text-blue-900">
                    בוגרים ותורמים מספרים
                </h2>
                <div class="grid md:grid-cols-2 gap-8">
                    <!-- כרטיס עדויות בוגרים -->
                    <div class="testimonial-card p-6 rounded-xl shadow-xl text-gray-700">
                        <!-- SVG של ציטוט -->
                        <svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8 text-yellow-500 mb-4" viewBox="0 0 24 24" fill="currentColor"><path d="M14 6H10v4h4V6zm0 6H10v4h4v-4zM7 6H3v4h4V6zm0 6H3v4h4v-4zM21 6h-4v4h4V6zm0 6h-4v4h4v-4z"/></svg>
                        <p class="italic mb-4 text-lg">
                            "השנים בישיבת אש קודש עיצבו את מי שאני היום. השילוב בין לימוד רציני בגמרא לבין סדרי חסידות נתן לי עומק ואמונה אמיתית להתמודד עם אתגרי החיים."
                        </p>
                        <p class="font-semibold text-blue-800">- יוסי לוי, בוגר מחזור תשע"ח</p>
                    </div>
                    
                    <!-- כרטיס עדויות תורמים -->
                    <div class="testimonial-card p-6 rounded-xl shadow-xl text-gray-700">
                        <!-- SVG של כסף/לב -->
                        <svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8 text-yellow-500 mb-4" viewBox="0 0 24 24" fill="currentColor"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/></svg>
                        <p class="italic mb-4 text-lg">
                            "הבנתי שהשקעה בישיבה הזו היא השקעה בעתיד הדור. שמחתי לראות איך התרומה שלי עוזרת לצעירים למצוא את דרכם בעולם התורה והמעשה. כל הכבוד לרבנים ולצוות."
                        </p>
                        <p class="font-semibold text-blue-800">- משפחת כהן, תורמים יקרים</p>
                    </div>
                </div>
                <div class="text-center mt-10">
                    <a href="#donate" class="text-blue-900 font-bold hover:text-yellow-600 transition duration-300 underline" role="button">
                        גם אתם יכולים להיות שותפים לחזון
                    </a>
                </div>
            </div>
        </section>

        <!-- 4. עדכונים ואירועים קרובים (Updates Section) -->
        <section id="updates" class="py-16 md:py-24 bg-gray-50 border-t border-b">
            <div class="container mx-auto px-4 max-w-6xl">
                <h2 class="text-4xl font-bold text-center mb-12 text-blue-900">
                    עדכונים ואירועים קרובים
                </h2>
                <!-- מיכל שמכיל את הפוסטים שירונדרו על ידי JavaScript -->
                <div id="updates-container" class="grid md:grid-cols-3 gap-8">
                    <!-- Posts will be injected here by JavaScript -->
                </div>
                <div class="text-center mt-12">
                    <!-- קישור פנימי - SEO 2.א -->
                    <a href="#contact" class="bg-blue-900 text-white py-3 px-8 rounded-full font-bold inline-block hover:bg-blue-800 transition duration-300 shadow-lg" role="button" aria-label="למעבר לעמוד צור קשר">
                        לכל העדכונים ופרטי רישום
                    </a>
                </div>
            </div>
        </section>

        <!-- 4.5. הרבנים שלנו (Rabbis Section) - חדש (סעיף 6) -->
        <section id="rabbis" class="bg-white py-16 md:py-24 border-t border-b">
            <div class="container mx-auto px-4 max-w-5xl">
                <!-- ****** עדכון: הורדת "והצוות הרוחני" והשארת "ראש הישיבה" בלבד ****** -->
                <h2 class="text-4xl font-bold text-center mb-12 text-blue-900">
                    ראש הישיבה
                </h2>
                <!-- הוסר ה-grid md:grid-cols-2 ונוסף flex justify-center כדי למרכז את הכרטיס היחיד שנותר -->
                <div class="flex justify-center">
                    
                    <!-- רב 1: ראש הישיבה - עדכון פרטים וביוגרפיה -->
                    <div class="bg-gray-50 p-6 rounded-xl shadow-lg border-t-4 border-yellow-500 w-full max-w-xl text-center">
                        <img src="https://placehold.co/150x150/1F3A60/FFFFFF?text=הרב+ואזאנא" alt="תמונת הרב אברהם ואזאנא, ראש הישיבה" class="rounded-full mx-auto mb-4 w-32 h-32 object-cover border-4 border-white shadow-md">
                        <!-- ****** עדכון: שם הרב ****** -->
                        <h3 class="text-2xl font-bold text-blue-900 mb-1">הרב אברהם ואזאנא</h3>
                        <p class="text-yellow-600 font-semibold mb-3">ראש ישיבת א"ש קודש</p>
                        
                        <!-- ****** עדכון: הוספת הביוגרפיה המלאה ****** -->
                        <div class="text-gray-700 text-base text-right leading-relaxed mt-4">
                            <p class="font-bold text-blue-800 mb-2">ביוגרפיה קצרה:</p>
                            <p class="mb-2">נולד בשנת התשל"א (1971) בבאר שבע, לאביו הרב אליהו ואזאנא מראשי תנועת המפד"ל בדרום. למד בישיבת בני עקיבא "אוהל שלמה" (וולפסון) והמשיך לישיבת ההסדר "כרם ביבנה" שם למד אצל הרב חיים יעקב גולדויכט והרב הראשי לישראל דאז הרב קלמן בר.</p>
                            
                            <p class="mb-2">הרב ואזאנא משמש כרב קהילת נווה יוסף חיים בשכונת נאות לון בעיר. בעבר שימש כראש תוכנית לימודי דיינות בכולל "בית מוריה" וכיהן כר"מ בתוכנית לבעלי תשובה "אורות ישראל".</p>
                            
                            <p class="mb-2">באלול תשס"ח (2008) הקים את תלמוד תורה "ארץ הצבי", ובשנת תשע"ז (2017) ייסד את ישיבת "א"ש קודש" כהמשך לתלמוד התורה.</p>
                            
                            <p class="mb-2">הרב למד קבלה אצל הרב לוי סעדיה נחמני זצ"ל והושפע ממנו מאוד. כמו כן, שימש במשך שנים רבות כ'חוזר' של הרב אלעזר אבוחצירא זצ"ל ("הבבא אלעזר") בשיעורים המצומצמים שהועברו למקורבי הרב אבוחצירא בימי שבת.</p>
                        </div>
                    </div>

                </div>
            </div>
        </section>


        <!-- 5. סדרים וזמני לימוד (Schedule Section) -->
        <section id="sedarim" class="bg-white py-16 md:py-24 border-t border-b">
            <div class="container mx-auto px-4 max-w-5xl">
                <h2 class="text-4xl font-bold text-center mb-12 text-blue-900">
                    זמני הלימוד היומיים בישיבה
                </h2>
                
                <!-- כפתורי בחירה (טאבים) - UX 1.ג -->
                <div class="flex flex-wrap justify-center gap-4 mb-8">
                    <button class="seder-tab bg-gray-200 text-blue-900 py-3 px-6 rounded-full font-bold transition hover:bg-gray-300 active" data-seder="morning" aria-controls="seder-details" aria-selected="true">
                        סדר בוקר
                    </button>
                    <button class="seder-tab bg-gray-200 text-blue-900 py-3 px-6 rounded-full font-bold transition hover:bg-gray-300" data-seder="afternoon" aria-controls="seder-details" aria-selected="false">
                        סדר צהריים
                    </button>
                    <button class="seder-tab bg-gray-200 text-blue-900 py-3 px-6 rounded-full font-bold transition hover:bg-gray-300" data-seder="evening" aria-controls="seder-details" aria-selected="false">
                        סדר ערב
                    </button>
                </div>

                <!-- תוכן דינמי של הסדרים - AJAX-like (UX 1.ג) -->
                <!-- הוסר טקסט הפלייסמנט מתוך ה-HTML כדי למנוע הבהוב -->
                <div id="seder-details" class="bg-blue-900 text-white p-6 md:p-10 rounded-xl shadow-2xl transition duration-500 transform hover:scale-[1.01]">
                    <!-- ייטען על ידי JavaScript מיד בטעינה -->
                </div>
            </div>
        </section>

        <!-- 6. קטע תרומה (Donation Section) -->
        <section id="donate" class="bg-gray-100 py-16 md:py-24">
            <div class="container mx-auto px-4 text-center max-w-4xl">
                <h2 class="text-4xl font-bold mb-6 text-blue-900">
                    שותפים בבניין עולם התורה
                </h2>
                <p class="text-xl text-gray-700 mb-8">
                    בזכותכם אנו ממשיכים להגדיל תורה ולהאדירה. כל תרומה היא אבן יסוד המאפשרת את המשך הלימוד והצמיחה הרוחנית של תלמידינו. תמכו בנו וקחו חלק באש הקודש!
                </p>
                <!-- סעיף 9: טקסט מפורט ל-SEO ולשכנוע - חדש -->
                <div class="bg-white p-6 rounded-xl shadow-inner mb-8 text-right border-l-4 border-yellow-500">
                    <h3 class="text-2xl font-bold text-blue-900 mb-3">יעדי התרומה: לאן הכסף שלכם הולך?</h3>
                    <!-- ****** עדכון: הוסרה כל רשימת הפעילויות כפי שביקשת ****** -->
                    <p class="text-gray-700">
                        כספי התרומות משמשים להפעלת המסגרת התורנית, הפנימייתית והלימודית של הישיבה, ומבטיחים את המשך גידול הדור הבא של מנהיגי עם ישראל. 
                    </p>
                </div>

                <a href="#contact" class="btn-primary py-4 px-10 text-2xl rounded-full font-bold shadow-xl hover:scale-105 inline-block" role="button" aria-label="מעבר לטופס תרומה מאובטח">
                    תרמו עכשיו והיו שותפים
                </a>
            </div>
        </section>

        <!-- 7. צור קשר (Contact Section) -->
        <section id="contact" class="py-16 md:py-24">
            <div class="container mx-auto px-4 max-w-6xl">
                <h2 class="text-4xl font-bold text-center mb-10 border-b-4 border-yellow-400 inline-block pb-1 text-blue-900">
                    צרו איתנו קשר
                </h2>
                <div class="grid md:grid-cols-2 gap-8 text-lg">
                    <!-- פרטי יצירת קשר -->
                    <div class="space-y-4 bg-white p-6 rounded-xl shadow-lg border border-gray-200 transition duration-300 hover:shadow-xl">
                        <h3 class="font-bold text-2xl text-blue-900">פרטי הישיבה</h3>
                        <p>
                            <span class="font-semibold text-yellow-500">כתובת:</span> רחוב התלמוד 2, באר שבע
                        </p>
                        <p>
                            <span class="font-semibold text-yellow-500">טלפון:</span> 08-6411041
                        </p>
                        <p>
                            <span class="font-semibold text-yellow-500">דוא"ל:</span> office@ohelshlomo.co.il
                        </p>
                        <p class="pt-4">
                            נשמח לשמוע מכם ולענות על כל שאלה.
                        </p>

                        <!-- סעיף 4: הטמעת מפת גוגל אינטראקטיבית - חדש -->
                        <h4 class="font-bold text-xl text-blue-900 pt-6">מפת הגעה</h4>
                        <!-- שימוש ב-iframe של גוגל מפות לכתובת מרכזית בבאר שבע -->
                        <div class="aspect-w-16 aspect-h-9 w-full h-64 rounded-lg overflow-hidden border border-gray-300 shadow-md">
                            <iframe 
                                src="https://maps.google.com/maps?q=%D7%94%D7%AA%D7%9C%D7%9E%D7%95%D7%93%202,%20%D7%91%D7%90%D7%A8%20%D7%A9%D7%91%D7%A2&t=&z=15&ie=UTF8&iwloc=&output=embed" 
                                width="100%" 
                                height="100%" 
                                style="border:0;" 
                                allowfullscreen="" 
                                loading="lazy" 
                                referrerpolicy="no-referrer-when-downgrade"
                                aria-label="מפת הגעה לישיבת אש קודש, רחוב התלמוד 2, באר שבע"
                            ></iframe>
                        </div>
                    </div>

                    <!-- טופס יצירת קשר עם השלמה אוטומטית (5.ב) -->
                    <div class="bg-white p-6 rounded-xl shadow-lg border border-gray-200 transition duration-300 hover:shadow-xl">
                        <h3 class="font-bold text-2xl text-blue-900 mb-4">שלחו לנו הודעה</h3>
                        <form id="contact-form" action="#" method="POST" class="space-y-4">
                            <div>
                                <label for="name" class="block text-sm font-medium text-gray-700">שם מלא:</label>
                                <!-- השלמה אוטומטית -->
                                <input type="text" id="name" name="name" required class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-2 border focus:border-blue-500 focus:ring focus:ring-blue-500 focus:ring-opacity-50" autocomplete="name">
                            </div>
                            <div>
                                <label for="email" class="block text-sm font-medium text-gray-700">דוא"ל:</label>
                                <!-- השלמה אוטומטית -->
                                <input type="email" id="email" name="email" required class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-2 border focus:border-blue-500 focus:ring focus:ring-blue-500 focus:ring-opacity-50" autocomplete="email">
                            </div>
                            <div>
                                <label for="city" class="block text-sm font-medium text-gray-700">עיר מגורים:</label>
                                <!-- השלמה אוטומטית עם datalist -->
                                <input type="text" id="city" name="city" required class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-2 border focus:border-blue-500 focus:ring focus:ring-blue-500 focus:ring-opacity-50" list="cities" autocomplete="address-level2">
                                <datalist id="cities">
                                    <option value="באר שבע">
                                    <option value="תל אביב">
                                    <option value="ירושלים">
                                    <option value="אשדוד">
                                    <option value="אילת">
                                </datalist>
                            </div>
                            <div>
                                <label for="message" class="block text-sm font-medium text-gray-700">הודעה:</label>
                                <textarea id="message" name="message" rows="4" required class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-2 border focus:border-blue-500 focus:ring focus:ring-blue-500 focus:ring-opacity-50"></textarea>
                            </div>
                            <button type="submit" class="btn-primary w-full py-2 px-4 rounded-lg font-bold" role="button">
                                שלח הודעה
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </section>

        <!-- מודל הודעת אישור (במקום alert) -->
        <div id="message-modal" class="fixed inset-0 bg-gray-900 bg-opacity-75 flex items-center justify-center z-[100] transition duration-300" role="dialog" aria-modal="true" aria-labelledby="modal-title">
            <div class="bg-white p-8 rounded-xl shadow-2xl text-center max-w-sm w-full transform scale-100">
                <div class="text-4xl text-blue-700 mb-4">
                    <!-- SVG של אישור (Check) -->
                    <svg xmlns="http://www.w3.org/2000/svg" class="mx-auto" width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/><path d="m9 11 3 3L22 4"/></svg>
                </div>
                <h3 id="modal-title" class="text-2xl font-bold mb-3 text-blue-900">ההודעה נשלחה בהצלחה!</h3>
                <p class="text-gray-700 mb-6">
                    תודה שפניתם אלינו. נשתדל לחזור אליכם בהקדם האפשרי.
                </p>
                <button id="close-modal-btn" class="bg-blue-900 text-white py-2 px-6 rounded-lg font-semibold hover:bg-blue-800 transition" role="button">
                    סגור
                </button>
            </div>
        </div>

    </div> <!-- סוף main-content -->

    <!-- כפתור צ'אט חי צף (5.א) - מדומה -->
    <button id="live-chat-btn" class="p-4 rounded-full" aria-label="פתח צ'אט חי">
        <!-- SVG אייקון הודעה -->
        <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M7.9 20A9 9 0 1 0 4 16.1L2 22Z"/></svg>
    </button>

    <!-- 8. פוטר (Footer) -->
    <footer class="bg-blue-900 text-white py-8">
        <div class="container mx-auto px-4 text-center">
            <p class="text-lg mb-2">
                &copy; 2024 ישיבת אש קודש לצעירים, באר שבע. כל הזכויות שמורות.
            </p>
            <div class="flex justify-center space-x-4 space-x-reverse text-sm text-yellow-400">
                <a href="#about" class="hover:underline nav-link" data-target="about">אודות</a>
                <span>|</span>
                <a href="#contact" class="hover:underline nav-link" data-target="contact">מדיניות פרטיות</a>
            </div>
        </div>
    </footer>

    <!-- סקריפט JavaScript לפונקציונליות אינטראקטיבית ודינמית -->
    <script>
        // --- 0. נתונים מדומי ---
        
        // נתוני עדכונים (מדמים API)
        const updatesData = [
            {
                title: "שיעור מיוחד לרגל ראש חודש כסלו",
                date: "חמישי, 10 בדצמבר",
                summary: "הרב הראשי ימסור שיעור מיוחד בענייני התחדשות חודש כסלו והכנה לחנוכה. הציבור מוזמן!",
                category: "אירוע"
            },
            {
                title: "יציאה לשבת חבורה באזור הדרום",
                date: "25-26 בדצמבר",
                summary: "שבת ישיבה מלאה עם סדרי חסידות, תפילות משותפות וטיול קצר. חובה להירשם מראש.",
                category: "טיול"
            },
            {
                title: "סיכום סדר עיון מסכת בבא קמא",
                date: "1 בדצמבר",
                summary: "בסייעתא דשמיא, סיימנו את סדר העיון במסכת המאתגרת. תודה לתלמידים על ההתמדה והיגיעה.",
                category: "סיכום לימוד"
            }
        ];

        // נתוני סדרים (מדמים AJAX / טעינה דינמית) - עדכון להדגשת בגרויות
        const sedarimData = {
            morning: {
                title: "סדר בוקר: גמרא בעיון מעמיק", 
                subtitle: "לימוד גמרא בעיון מעמיק והכנה לחיי מעשה",
                details: [
                    { time: "7:30", activity: "תפילת שחרית" },
                    { time: "9:00 - 10:30", activity: "סדר עיון: גמרא" }, 
                    { time: "11:00", activity: "שיעור כללי" }
                ]
            },
            afternoon: {
                // ****** שינוי: הבלטת הכנה לבגרויות ******
                title:  "סדר צהריים: לימודי תיכון והשלמת בגרות",
                subtitle: "לימודי בקיאות והכנה מקצועית לבגרויות",
                details: [
                    { time: "12:30", activity: "תפילת מנחה" },
                    // 15:30-18:00
                    { time: "13:40 - 15:00", activity: "לימוד בקיאות והלכה" }, 
                    // ****** שינוי: פירוט לימודי תיכון ******
                    { time: "15:20 - 18:30", activity: "לימודי תיכון מורחבים והכנה מלאה לבחינות הבגרות" }
                ]
            },
            evening: {
                title: "סדר ערב: הלכה ודיבוק חברים", 
                subtitle: "הלכה ולימוד מתוך שמחה ודיבוק חברים",
                details: [
                    { time: "20:00", activity: "תפילת ערבית" },
                    // 20:30-22:00
                    { time: "20:30 - 22:00", activity: "סדר הלכה ולימוד מוסר" },
                    { time: "22:00", activity: "לימוד חבורות" }
                ]
            }
        };

        // --- 1. רינדור העדכונים ---
        const renderUpdates = () => {
            const container = document.getElementById('updates-container');
            if (!container) return; // הגנה: מוודא שהאלמנט קיים

            container.innerHTML = updatesData.map(update => {
                let categoryClasses;
                if (update.category === 'אירוע') {
                    categoryClasses = 'bg-red-100 text-red-800';
                } else if (update.category === 'טיול') {
                    categoryClasses = 'bg-green-100 text-green-800';
                } else {
                    categoryClasses = 'bg-blue-100 text-blue-800';
                }

                return `
                    <div class="bg-white p-6 rounded-xl shadow-lg border border-gray-200 transition duration-300 hover:shadow-2xl hover:scale-[1.02]">
                        <span class="inline-block px-3 py-1 text-xs font-semibold rounded-full mb-2 ${categoryClasses}">
                            ${update.category}
                        </span>
                        <h3 class="text-xl font-bold text-blue-900 mb-2">${update.title}</h3>
                        <p class="text-sm text-gray-500 mb-4">${update.date}</p>
                        <p class="text-gray-700">${update.summary}</p>
                        <a href="#" class="mt-4 text-sm text-yellow-600 font-semibold hover:text-yellow-700 block transition" aria-label="קרא עוד על: ${update.title}">קרא עוד »</a>
                    </div>
                `;
            }).join('');
        };

        // --- 2. לוגיקת טעינת סדרים דינמית ---
        /**
         * מרנדר את פרטי הסדר הנבחר.
         * @param {string} sederKey - המפתח של הסדר (morning, afternoon, evening).
         * @param {boolean} [animate=true] - האם לבצע אנימציית דהייה (fade) (רק במעבר בין טאבים).
         */
        const renderSederDetails = (sederKey, animate = true) => {
            const container = document.getElementById('seder-details');
            const data = sedarimData[sederKey];

            if (!container || !data) return; 

            // יצירת תוכן הדינמי
            const detailsHtml = data.details.map(item => `
                <li class="flex justify-between items-start border-b border-blue-700 py-3">
                    <span class="text-xl font-bold text-yellow-400 w-1/4 min-w-[80px]">${item.time}</span>
                    <span class="text-lg w-3/4 pr-4">${item.activity}</span>
                </li>
            `).join('');

            const newContent = `
                <h3 class="text-3xl md:text-4xl font-extrabold text-yellow-400 mb-2">${data.title}</h3>
                <p class="text-xl font-light mb-6">${data.subtitle}</p>
                <ul class="space-y-2 list-none">
                    ${detailsHtml}
                </ul>
            `;

            const updateContent = () => {
                container.innerHTML = newContent;
                if (animate) {
                    container.classList.remove('opacity-0'); // מופיע לאחר העדכון
                }
            };
            
            // אם זו טעינה ראשונית (animate=false), מעדכן מיד.
            if (animate) {
                container.classList.add('opacity-0'); // מסתיר לפני העדכון
                setTimeout(updateContent, 300); // מעדכן ומציג לאחר השהיה
            } else {
                updateContent(); // מעדכן מיד
            }

            // עדכון כפתורי הטאבים
            document.querySelectorAll('.seder-tab').forEach(tab => {
                const isActive = tab.dataset.seder === sederKey;
                tab.classList.toggle('active', isActive);
                tab.setAttribute('aria-selected', isActive);
            });
        };


        // --- 3. לוגיקת תפריט חכם (Smart Nav) - UX 1.א ---
        const setActiveLink = () => {
            // אוסף את כל הקטעים והקישורים רק פעם אחת לאחר הטעינה
            const sections = document.querySelectorAll('section[id]:not(#home)'); // קטעים עם ID, פרט ל-home
            const allNavLinks = document.querySelectorAll('.nav-link, .mobile-nav-link');
            
            // שינוי ה-offset כדי להתאים לגובה ה-Navbar החדש (60px)
            const offset = 80; // סף של 80 פיקסלים מהחלק העליון

            let currentSectionId = 'home';
            

            // בדיקת המיקום הנוכחי
            sections.forEach(section => {
                if (section.id) {
                    const sectionTop = section.offsetTop;
                    // בדיקה אם המשתמש גלל מעבר לקטע הנוכחי
                    if (window.scrollY >= sectionTop - offset) {
                        currentSectionId = section.id;
                    }
                }
            });

            // הפעלת מחלקת active על הקישור המתאים
            allNavLinks.forEach(link => {
                // בדיקה אם הקישור הוא כפתור תרומה, ושומרים עליו שלא ייצבע אם הוא לא הקטע הפעיל
                const isDonateButton = link.classList.contains('btn-primary');
                
                if (link.dataset.target === currentSectionId && !isDonateButton) {
                    link.classList.add('active');
                } else if (!isDonateButton) {
                    link.classList.remove('active');
                }
            });
        };


        // --- 4. הגדרות ורכיבים כלליים - הפעלה בטוחה (DOMContentLoaded) ---
        document.addEventListener('DOMContentLoaded', () => {
            // אלמנטים
            const mobileMenuButton = document.getElementById('mobile-menu-button');
            const mobileMenu = document.getElementById('mobile-menu');
            const contactForm = document.getElementById('contact-form');
            const messageModal = document.getElementById('message-modal');
            const closeModalBtn = document.getElementById('close-modal-btn');
            const sederTabs = document.querySelectorAll('.seder-tab');
            const chatBtn = document.getElementById('live-chat-btn');
            
            // אתחול
            renderUpdates(); 
            // קריאה ראשונית ללא אנימציה (animate=false) כדי למנוע הבהוב/המתנה
            renderSederDetails('morning', false); 
            setActiveLink();

            // הפעלת הניווט החכם בזמן גלילה
            window.addEventListener('scroll', setActiveLink);


            // --- תפריט מובייל ---
            const toggleMobileMenu = () => {
                mobileMenu.classList.toggle('hidden');
                const isExpanded = mobileMenu.classList.contains('hidden') ? 'false' : 'true';
                mobileMenuButton.setAttribute('aria-expanded', isExpanded);
            };

            if (mobileMenuButton) {
                mobileMenuButton.addEventListener('click', toggleMobileMenu);
            }

            // סגירת התפריט בלחיצה על קישור בתוך התפריט
            if (mobileMenu) {
                mobileMenu.querySelectorAll('a').forEach(link => {
                    link.addEventListener('click', () => {
                        if (!mobileMenu.classList.contains('hidden')) {
                            toggleMobileMenu();
                        }
                    });
                });
            }

            // --- טאבים לסדרים ---
            sederTabs.forEach(tab => {
                tab.addEventListener('click', (e) => {
                    const sederKey = e.currentTarget.dataset.seder;
                    // קריאה עם אנימציה (animate=true)
                    renderSederDetails(sederKey, true); 
                });
            });


            // --- טופס יצירת קשר ומודל ---
            const closeMessageModal = () => {
                messageModal.classList.remove('active');
            }

            if (contactForm && messageModal && closeModalBtn) {
                contactForm.addEventListener('submit', function(event) {
                    event.preventDefault(); 
                    messageModal.classList.add('active');
                    closeModalBtn.focus(); 
                    contactForm.reset();
                });
                
                closeModalBtn.addEventListener('click', closeMessageModal);

                 // סגירת המודל בלחיצה על רקע כהה
                 messageModal.addEventListener('click', (e) => {
                    if (e.target === messageModal) {
                        closeMessageModal();
                        document.getElementById('contact-form').querySelector('button[type="submit"]').focus();
                    }
                });

                // נגישות: סגירת המודל בלחיצה על מקש ESC 
                document.addEventListener('keydown', (event) => {
                    if (event.key === 'Escape' && messageModal.classList.contains('active')) {
                        closeMessageModal();
                        document.getElementById('contact-form').querySelector('button[type="submit"]').focus();
                    }
                });
            }


             // --- כפתור צ'אט חי ---
             if (chatBtn) {
                chatBtn.addEventListener('click', () => {
                    console.log("Chat initiated. This would open a chat window (e.g., Tawk.to widget).");
                    // הודעה מדומה
                    chatBtn.textContent = "הצ'אט נפתח!"; 
                    setTimeout(() => chatBtn.innerHTML = '<svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M7.9 20A9 9 0 1 0 4 16.1L2 22Z"/></svg>', 2000);
                });
             }
        });
    </script>

</body>
</html>
