<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PedSafeDose - دليل الجرعات الدوائية للأطفال</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #2c6fbb;
            --secondary: #4a90e2;
            --accent: #ff6b6b;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #28a745;
            --warning: #ffc107;
            --danger: #dc3545;
            --gray: #6c757d;
            --light-gray: #e9ecef;
        }
        
        body {
            background-color: #f5f7fa;
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1rem 0;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo i {
            font-size: 2.2rem;
            color: white;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        .logo span {
            color: var(--warning);
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-weight: 600;
            padding: 8px 12px;
            border-radius: 4px;
            transition: all 0.3s ease;
        }
        
        nav a:hover, nav a.active {
            background: rgba(255,255,255,0.2);
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(44, 111, 187, 0.9), rgba(74, 144, 226, 0.9)), url('https://placehold.co/1200x400/2c6fbb/ffffff?text=Pediatric+Medication') no-repeat center center/cover;
            color: white;
            padding: 4rem 0;
            text-align: center;
        }
        
        .hero h2 {
            font-size: 2.8rem;
            margin-bottom: 1.5rem;
            font-weight: 800;
        }
        
        .hero p {
            font-size: 1.3rem;
            max-width: 800px;
            margin: 0 auto 2rem;
            opacity: 0.9;
        }
        
        .warning-box {
            background: rgba(220, 53, 69, 0.2);
            border: 2px solid var(--danger);
            border-radius: 10px;
            padding: 1.5rem;
            margin-top: 2rem;
            display: inline-block;
            max-width: 800px;
        }
        
        .warning-box h3 {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
            color: var(--danger);
        }
        
        /* Main Content */
        main {
            padding: 3rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 2.5rem;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.2rem;
            color: var(--primary);
            display: inline-block;
            padding-bottom: 10px;
        }
        
        .section-title h2:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--secondary);
            border-radius: 2px;
        }
        
        /* Search Section */
        .search-section {
            background: white;
            border-radius: 12px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            margin-bottom: 3rem;
        }
        
        .search-container {
            display: flex;
            max-width: 700px;
            margin: 0 auto;
        }
        
        .search-container input {
            flex: 1;
            padding: 15px 20px;
            border: 2px solid var(--light-gray);
            border-radius: 8px 0 0 8px;
            font-size: 1.1rem;
            outline: none;
            transition: border-color 0.3s;
        }
        
        .search-container input:focus {
            border-color: var(--secondary);
        }
        
        .search-container button {
            background: var(--primary);
            color: white;
            border: none;
            padding: 0 25px;
            border-radius: 0 8px 8px 0;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s;
        }
        
        .search-container button:hover {
            background: var(--secondary);
        }
        
        /* Age Groups Navigation */
        .age-navigation {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            justify-content: center;
            margin-bottom: 2rem;
            overflow-x: auto;
            padding-bottom: 10px;
        }
        
        .age-btn {
            background: var(--light);
            border: 1px solid var(--light-gray);
            padding: 8px 16px;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 600;
            white-space: nowrap;
        }
        
        .age-btn:hover, .age-btn.active {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
        }
        
        /* Age Groups Content */
        .age-content {
            display: none;
            background: white;
            border-radius: 12px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            margin-bottom: 3rem;
        }
        
        .age-content.active {
            display: block;
        }
        
        .med-table {
            width: 100%;
            border-collapse: collapse;
        }
        
        .med-table th {
            background: var(--primary);
            color: white;
            text-align: right;
            padding: 1rem;
            font-weight: 600;
        }
        
        .med-table td {
            padding: 1rem;
            border-bottom: 1px solid var(--light-gray);
        }
        
        .med-table tr:last-child td {
            border-bottom: none;
        }
        
        .med-table tr:nth-child(even) {
            background-color: #f8f9fa;
        }
        
        .drug-name {
            font-weight: 700;
            color: var(--primary);
        }
        
        .warning-cell {
            color: var(--danger);
            font-weight: 600;
        }
        
        /* Critical Warnings */
        .warnings-table {
            width: 100%;
            border-collapse: collapse;
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            margin-bottom: 3rem;
        }
        
        .warnings-table th {
            background: var(--danger);
            color: white;
            text-align: right;
            padding: 1.2rem;
            font-weight: 600;
        }
        
        .warnings-table td {
            padding: 1.2rem;
            border-bottom: 1px solid var(--light-gray);
        }
        
        .warnings-table tr:last-child td {
            border-bottom: none;
        }
        
        .warnings-table tr:nth-child(even) {
            background-color: #fff9f9;
        }
        
        .reason {
            color: var(--danger);
            font-weight: 600;
        }
        
        /* References */
        .references {
            background: white;
            border-radius: 12px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }
        
        .ref-list {
            list-style: none;
            padding-right: 1.5rem;
        }
        
        .ref-list li {
            padding: 12px 0;
            border-bottom: 1px solid var(--light-gray);
            position: relative;
            padding-right: 25px;
        }
        
        .ref-list li:before {
            content: "•";
            color: var(--primary);
            position: absolute;
            right: 0;
            font-size: 1.5rem;
            line-height: 1;
        }
        
        .ref-list li:last-child {
            border-bottom: none;
        }
        
        /* Contact Section */
        .contact-section {
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            border-radius: 12px;
            padding: 2.5rem;
            margin-top: 2rem;
        }
        
        .contact-form {
            max-width: 700px;
            margin: 0 auto;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }
        
        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid var(--light-gray);
            border-radius: 8px;
            font-size: 1rem;
            outline: none;
            transition: border-color 0.3s;
        }
        
        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            border-color: var(--secondary);
        }
        
        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        .submit-btn {
            background: var(--primary);
            color: white;
            border: none;
            padding: 14px 30px;
            border-radius: 8px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: background 0.3s;
            display: block;
            margin: 0 auto;
        }
        
        .submit-btn:hover {
            background: var(--secondary);
        }
        
        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 2.5rem 0 1.5rem;
            margin-top: 3rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 2rem;
        }
        
        .footer-column h3 {
            font-size: 1.4rem;
            margin-bottom: 1.5rem;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3:after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 50px;
            height: 3px;
            background: var(--secondary);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 12px;
        }
        
        .footer-column ul li a {
            color: #adb5bd;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column ul li a:hover {
            color: white;
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid #343a40;
            color: #adb5bd;
            font-size: 0.95rem;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 15px;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero h2 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
            
            .search-container {
                flex-direction: column;
                gap: 10px;
            }
            
            .search-container input,
            .search-container button {
                width: 100%;
                border-radius: 8px;
            }
            
            .med-table {
                display: block;
                overflow-x: auto;
            }
        }
        
        @media (max-width: 480px) {
            .logo h1 {
                font-size: 1.5rem;
            }
            
            .hero {
                padding: 2.5rem 0;
            }
            
            .hero h2 {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-baby"></i>
                    <h1>Ped<span>Safe</span>Dose</h1>
                </div>
                <nav>
                    <ul>
                        <li><a href="#" class="active">الرئيسية</a></li>
                        <li><a href="#age-groups">الجرعات حسب العمر</a></li>
                        <li><a href="#warnings">تحذيرات حرجة</a></li>
                        <li><a href="#references">المراجع</a></li>
                        <li><a href="#contact">للتواصل</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h2>دليل الجرعات الدوائية للأطفال من الولادة حتى 12 سنة</h2>
            <p>مرجع موثوق لمقدمي الرعاية الصحية لضمان سلامة الأدوية الموصوفة للأطفال</p>
            
            <div class="warning-box">
                <h3><i class="fas fa-exclamation-triangle"></i> تحذير هام</h3>
                <p>يجب التحقق من العمر الأدنى للبدء بالعلاج لكل دواء. بعض الأدوية ممنوعة تمامًا في فئات عمرية معينة بسبب مخاطر صحية جسيمة.</p>
            </div>
        </div>
    </section>

    <!-- Main Content -->
    <main class="container">
        <!-- Search Section -->
        <section class="search-section">
            <h2 style="text-align: center; margin-bottom: 1.5rem; color: var(--primary);">ابحث عن دواء</h2>
            <div class="search-container">
                <input type="text" id="drug-search" placeholder="اكتب اسم الدواء (تجاري أو علمي)">
                <button id="search-btn"><i class="fas fa-search"></i> بحث</button>
            </div>
        </section>

        <!-- Age Groups Section -->
        <section id="age-groups">
            <div class="section-title">
                <h2>الجرعات حسب الفئة العمرية</h2>
            </div>
            
            <div class="age-navigation">
                <!-- Months -->
                <button class="age-btn active" data-age="0">0 شهر</button>
                <button class="age-btn" data-age="1">1 شهر</button>
                <button class="age-btn" data-age="2">2 شهر</button>
                <button class="age-btn" data-age="3">3 أشهر</button>
                <button class="age-btn" data-age="4">4 أشهر</button>
                <button class="age-btn" data-age="5">5 أشهر</button>
                <button class="age-btn" data-age="6">6 أشهر</button>
                <button class="age-btn" data-age="7">7 أشهر</button>
                <button class="age-btn" data-age="8">8 أشهر</button>
                <button class="age-btn" data-age="9">9 أشهر</button>
                <button class="age-btn" data-age="10">10 أشهر</button>
                <button class="age-btn" data-age="11">11 شهر</button>
                <button class="age-btn" data-age="12">12 شهر</button>
                
                <!-- Years -->
                <button class="age-btn" data-age="13">1 سنة</button>
                <button class="age-btn" data-age="24">2 سنة</button>
                <button class="age-btn" data-age="36">3 سنوات</button>
                <button class="age-btn" data-age="48">4 سنوات</button>
                <button class="age-btn" data-age="60">5 سنوات</button>
                <button class="age-btn" data-age="72">6 سنوات</button>
                <button class="age-btn" data-age="84">7 سنوات</button>
                <button class="age-btn" data-age="96">8 سنوات</button>
                <button class="age-btn" data-age="108">9 سنوات</button>
                <button class="age-btn" data-age="120">10 سنوات</button>
                <button class="age-btn" data-age="132">11 سنة</button>
                <button class="age-btn" data-age="144">12 سنة</button>
            </div>
            
            <!-- Age Content Sections -->
            <div id="age-0" class="age-content active">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لحديثي الولادة (0 شهر)</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin K</td>
                            <td>Phytonadione</td>
                            <td>1 مغ حقن عضلي عند الولادة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Erythromycin Ointment</td>
                            <td>Erythromycin</td>
                            <td>للعينين بعد الولادة مباشرة</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-1" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 1 شهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-2" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 2 شهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-3" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 3 أشهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-4" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 4 أشهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب قبل 6 أشهر</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-5" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 5 أشهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب قبل 6 أشهر</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-6" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 6 أشهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">السلامة والفعالية غير مثبتة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.25-0.5 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>3-10 قطرات ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-7" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 7 أشهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">السلامة والفعالية غير مثبتة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.25-0.5 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>3-10 قطرات ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-8" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 8 أشهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">السلامة والفعالية غير مثبتة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.25-0.5 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>3-10 قطرات ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-9" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 9 أشهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">السلامة والفعالية غير مثبتة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.25-0.5 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>3-10 قطرات ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-10" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 10 أشهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">السلامة والفعالية غير مثبتة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.25-0.5 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>3-10 قطرات ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-11" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 11 شهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">السلامة والفعالية غير مثبتة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.25-0.5 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>3-10 قطرات ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-12" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 12 شهر</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">السلامة والفعالية غير مثبتة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.25-0.5 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td class="warning-cell">غير موصى به قبل سنتين</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td class="warning-cell">غير موصى به قبل سنتين</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>3-10 قطرات ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-13" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 1 سنة</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">السلامة والفعالية غير مثبتة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.25-0.5 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td class="warning-cell">غير موصى به قبل سنتين</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td class="warning-cell">غير موصى به قبل سنتين</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>4 مغ يوميًا</td>
                            <td class="warning-cell">غير موصى به قبل سنتين</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">غير موصى به قبل سنتين</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>10-15 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-24" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 2 سنة</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400-600 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>2.5-5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>غير موصى به</td>
                            <td class="warning-cell">السلامة والفعالية غير مثبتة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.25-0.5 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>4 مغ يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>2.5 مل شراب ثلاث مرات يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ryaltris</td>
                            <td>Olopatadine/Mometasone</td>
                            <td>رشتان في كل فتحة أنف مرتين يوميًا</td>
                            <td class="warning-cell">غير موصى به قبل سنتين</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>10-15 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-36" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 3 سنوات</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400-600 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>5 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>2 مغ مرة واحدة (للوزن 8-15 كغ)</td>
                            <td class="warning-cell">استخدام خارج التسمية للإسهال الحاد</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.5-1 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>4 مغ يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>2.5 مل شراب ثلاث مرات يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ryaltris</td>
                            <td>Olopatadine/Mometasone</td>
                            <td>رشتان في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Flixotide Evohaler</td>
                            <td>Fluticasone</td>
                            <td>50-100 mcg مرتين يوميًا</td>
                            <td class="warning-cell">غير موصى به قبل 4 سنوات</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>15-20 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-48" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 4 سنوات</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400-600 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>5-10 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>4 مغ 30 دقيقة قبل العلاج الكيميائي، ثم 4 و8 ساعات بعد الجرعة الأولى، ثم كل 8 ساعات لمدة 1-2 أيام</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.5-1 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>4-5 مغ يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>5 مل مرتين إلى ثلاث مرات يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ryaltris</td>
                            <td>Olopatadine/Mometasone</td>
                            <td>رشتان في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Flixotide Evohaler</td>
                            <td>Fluticasone</td>
                            <td>50-125 mcg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>15-20 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-60" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 5 سنوات</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400-600 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>5-10 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>4 مغ 30 دقيقة قبل العلاج الكيميائي، ثم 4 و8 ساعات بعد الجرعة الأولى، ثم كل 8 ساعات لمدة 1-2 أيام</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.5-1 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>5 مغ يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>5 مل مرتين إلى ثلاث مرات يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ryaltris</td>
                            <td>Olopatadine/Mometasone</td>
                            <td>رشتان في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Flixotide Evohaler</td>
                            <td>Fluticasone</td>
                            <td>100-125 mcg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Klacid XL</td>
                            <td>Clarithromycin</td>
                            <td>7.5 مغ/كغ كل 12 ساعة</td>
                            <td class="warning-cell">غير موصى به قبل 12 سنة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>15-20 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-72" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 6 سنوات</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400-600 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>10 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>4 مغ 30 دقيقة قبل العلاج الكيميائي، ثم 4 و8 ساعات بعد الجرعة الأولى، ثم كل 8 ساعات لمدة 1-2 أيام</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.5-1 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>5 مغ يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>5 مل مرتين إلى ثلاث مرات يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ryaltris</td>
                            <td>Olopatadine/Mometasone</td>
                            <td>رشتان في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Flixotide Evohaler</td>
                            <td>Fluticasone</td>
                            <td>100-125 mcg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Klacid XL</td>
                            <td>Clarithromycin</td>
                            <td>7.5 مغ/كغ كل 12 ساعة</td>
                            <td class="warning-cell">غير موصى به قبل 12 سنة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>15-20 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-84" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 7 سنوات</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400-600 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>10 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>4 مغ 30 دقيقة قبل العلاج الكيميائي، ثم 4 و8 ساعات بعد الجرعة الأولى، ثم كل 8 ساعات لمدة 1-2 أيام</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.5-1 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>5 مغ يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>5 مل مرتين إلى ثلاث مرات يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ryaltris</td>
                            <td>Olopatadine/Mometasone</td>
                            <td>رشتان في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Flixotide Evohaler</td>
                            <td>Fluticasone</td>
                            <td>125 mcg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Klacid XL</td>
                            <td>Clarithromycin</td>
                            <td>7.5 مغ/كغ كل 12 ساعة</td>
                            <td class="warning-cell">غير موصى به قبل 12 سنة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>15-20 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-96" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 8 سنوات</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400-600 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>10 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>4 مغ 30 دقيقة قبل العلاج الكيميائي، ثم 4 و8 ساعات بعد الجرعة الأولى، ثم كل 8 ساعات لمدة 1-2 أيام</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.5-1 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>5 مغ يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>5 مل مرتين إلى ثلاث مرات يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ryaltris</td>
                            <td>Olopatadine/Mometasone</td>
                            <td>رشتان في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Flixotide Evohaler</td>
                            <td>Fluticasone</td>
                            <td>125 mcg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Klacid XL</td>
                            <td>Clarithromycin</td>
                            <td>7.5 مغ/كغ كل 12 ساعة</td>
                            <td class="warning-cell">غير موصى به قبل 12 سنة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>15-20 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-108" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 9 سنوات</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400-600 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>10 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>4 مغ 30 دقيقة قبل العلاج الكيميائي، ثم 4 و8 ساعات بعد الجرعة الأولى، ثم كل 8 ساعات لمدة 1-2 أيام</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.5-1 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>5 مغ يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>5 مل مرتين إلى ثلاث مرات يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ryaltris</td>
                            <td>Olopatadine/Mometasone</td>
                            <td>رشتان في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Flixotide Evohaler</td>
                            <td>Fluticasone</td>
                            <td>125 mcg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Klacid XL</td>
                            <td>Clarithromycin</td>
                            <td>7.5 مغ/كغ كل 12 ساعة</td>
                            <td class="warning-cell">غير موصى به قبل 12 سنة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>15-20 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-120" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 10 سنوات</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400-600 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>10 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>4 مغ 30 دقيقة قبل العلاج الكيميائي، ثم 4 و8 ساعات بعد الجرعة الأولى، ثم كل 8 ساعات لمدة 1-2 أيام</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.5-1 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>5 مغ يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>5 مل مرتين إلى ثلاث مرات يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ryaltris</td>
                            <td>Olopatadine/Mometasone</td>
                            <td>رشتان في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Flixotide Evohaler</td>
                            <td>Fluticasone</td>
                            <td>125 mcg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Klacid XL</td>
                            <td>Clarithromycin</td>
                            <td>7.5 مغ/كغ كل 12 ساعة</td>
                            <td class="warning-cell">غير موصى به قبل 12 سنة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>15-20 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-132" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 11 سنة</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400-600 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>10 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>4 مغ 30 دقيقة قبل العلاج الكيميائي، ثم 4 و8 ساعات بعد الجرعة الأولى، ثم كل 8 ساعات لمدة 1-2 أيام</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.5-1 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>5 مغ يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>5 مل مرتين إلى ثلاث مرات يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ryaltris</td>
                            <td>Olopatadine/Mometasone</td>
                            <td>رشتان في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Flixotide Evohaler</td>
                            <td>Fluticasone</td>
                            <td>125 mcg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Klacid XL</td>
                            <td>Clarithromycin</td>
                            <td>7.5 مغ/كغ كل 12 ساعة</td>
                            <td class="warning-cell">غير موصى به قبل 12 سنة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>0.5-1 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>15-20 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div id="age-144" class="age-content">
                <h3 style="margin-bottom: 1.5rem; color: var(--primary);">الأدوية المسموح بها لعمر 12 سنة</h3>
                <table class="med-table">
                    <thead>
                        <tr>
                            <th>الدواء</th>
                            <th>الاسم العلمي</th>
                            <th>الجرعة</th>
                            <th>التحذيرات</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="drug-name">Paracetamol</td>
                            <td>Acetaminophen</td>
                            <td>10-15 مغ/كغ كل 6-8 ساعات</td>
                            <td class="warning-cell">تجنب الجرعات العالية</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Vitamin D</td>
                            <td>Cholecalciferol</td>
                            <td>400-600 وحدة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Amoxicillin</td>
                            <td>Amoxicillin</td>
                            <td>20-40 مغ/كغ/يوم مقسمة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Cetirizine</td>
                            <td>Cetirizine</td>
                            <td>10 ملغ مرة يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ibuprofen</td>
                            <td>Ibuprofen</td>
                            <td>5-10 مغ/كغ كل 6-8 ساعات</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Zoron</td>
                            <td>Ondansetron</td>
                            <td>8 مغ 30 دقيقة قبل العلاج الكيميائي، ثم كل 12 ساعة لمدة 1-2 أيام</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Azimac</td>
                            <td>Azithromycin</td>
                            <td>10 مغ/كغ يوميًا لمدة 3 أيام</td>
                            <td class="warning-cell">تجنب في حديثي الولادة</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Pulmicort Nebulizer</td>
                            <td>Budesonide</td>
                            <td>0.5-1 mg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Decozal Nasal Drops</td>
                            <td>Xylometazoline</td>
                            <td>1-2 قطرة في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Tacroz Ointment</td>
                            <td>Tacrolimus</td>
                            <td>طبقتين رقيقتين مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Elica Cream</td>
                            <td>Mometasone</td>
                            <td>طبقتين رقيقتين مرة يوميًا</td>
                            <td class="warning-cell">تجنب الاستخدام المطول</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Airfast Chewable</td>
                            <td>Montelukast</td>
                            <td>5 مغ يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ambolar</td>
                            <td>Ambroxol</td>
                            <td>5 مل مرتين إلى ثلاث مرات يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ryaltris</td>
                            <td>Olopatadine/Mometasone</td>
                            <td>رشتان في كل فتحة أنف مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Flixotide Evohaler</td>
                            <td>Fluticasone</td>
                            <td>125-250 mcg مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Klacid XL</td>
                            <td>Clarithromycin</td>
                            <td>250-500 مغ كل 12 ساعة</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Polmena</td>
                            <td>Budesonide</td>
                            <td>1-2 مغ مرتين يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Ferose-F Tablet</td>
                            <td>Iron/Folic Acid</td>
                            <td>قرص واحد يوميًا</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Roxonin Tape</td>
                            <td>Lornoxicam</td>
                            <td>لصقة واحدة يوميًا</td>
                            <td class="warning-cell">تجنب في الأطفال</td>
                        </tr>
                        <tr>
                            <td class="drug-name">Fenistil Drops</td>
                            <td>Dimetindene</td>
                            <td>15-20 قطرة ثلاث مرات يوميًا</td>
                            <td class="warning-cell">خطر انقطاع النفس أثناء النوم</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <!-- Critical Warnings -->
        <section id="warnings">
            <div class="section-title">
                <h2>تحذيرات حرجة</h2>
            </div>
            
            <table class="warnings-table">
                <thead>
                    <tr>
                        <th>الدواء</th>
                        <th>السبب</th>
                        <th>المرجع</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="drug-name">Fenistil Drops</td>
                        <td class="reason">خطر انقطاع النفس أثناء النوم</td>
                        <td>EMA, Lexicomp</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Elica 0.1% Cream</td>
                        <td class="reason">خطر متلازمة كوشينغ الجهازية</td>
                        <td>FDA, BNF</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Zoron (Ondansetron)</td>
                        <td class="reason">السلامة والفعالية غير مثبتة للأطفال دون 4 سنوات</td>
                        <td>FDA Guidelines</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Roxonin Tape</td>
                        <td class="reason">خطر السمية الكلوية</td>
                        <td>AHA, UpToDate</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Flixotide Evohaler</td>
                        <td class="reason">غير موصى به قبل 4 سنوات</td>
                        <td>BNF for Children</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Decozal Nasal Drops</td>
                        <td class="reason">غير موصى به قبل سنتين</td>
                        <td>EMA Guidelines</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Tacroz Ointment</td>
                        <td class="reason">غير موصى به قبل سنتين</td>
                        <td>FDA, BNF</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Polmena</td>
                        <td class="reason">غير موصى به قبل 3 أشهر</td>
                        <td>Manufacturer Guidelines</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Ferose-F Tablet</td>
                        <td class="reason">غير مناسب للرضع</td>
                        <td>BNF for Children</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Airfast Chewable</td>
                        <td class="reason">غير موصى به قبل 6 سنوات</td>
                        <td>FDA, EMA</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Ryaltris</td>
                        <td class="reason">غير موصى به قبل سنتين</td>
                        <td>FDA, BNF</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Ambolar</td>
                        <td class="reason">غير موصى به قبل سنتين</td>
                        <td>Manufacturer Guidelines</td>
                    </tr>
                    <tr>
                        <td class="drug-name">Klacid XL</td>
                        <td class="reason">غير موصى به قبل 12 سنة</td>
                        <td>FDA, BNF</td>
                    </tr>
                </tbody>
            </table>
        </section>

        <!-- References -->
        <section id="references">
            <div class="section-title">
                <h2>المصادر والمراجع</h2>
            </div>
            
            <div class="references">
                <ul class="ref-list">
                    <li>BNF for Children (2025 edition)</li>
                    <li>UpToDate (Last updated: Jan 2026)</li>
                    <li>FDA Prescribing Information</li>
                    <li>European Medicines Agency (EMA)</li>
                    <li>Lexicomp / Micromedex</li>
                    <li>American Academy of Pediatrics (AAP) Guidelines</li>
                </ul>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact">
            <div class="section-title">
                <h2>للتواصل مع الصيادلة والمهنيين الصحيين</h2>
            </div>
            
            <div class="contact-section">
                <div class="contact-form">
                    <div class="form-group">
                        <label for="name">الاسم الكامل</label>
                        <input type="text" id="name" placeholder="أدخل اسمك">
                    </div>
                    <div class="form-group">
                        <label for="email">البريد الإلكتروني</label>
                        <input type="email" id="email" placeholder="أدخل بريدك الإلكتروني">
                    </div>
                    <div class="form-group">
                        <label for="specialty">التخصص</label>
                        <select id="specialty">
                            <option value="">اختر التخصص</option>
                            <option value="pharmacy">صيدلة</option>
                            <option value="pediatrics">طب الأطفال</option>
                            <option value="nursing">تمريض</option>
                            <option value="other">أخرى</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="message">الرسالة</label>
                        <textarea id="message" placeholder="اكتب استفسارك أو اقتراحك..."></textarea>
                    </div>
                    <button class="submit-btn">إرسال الرسالة</button>
                </div>
            </div>
            
            <div style="background: #e9f7ef; border-radius: 10px; padding: 1.5rem; margin-top: 2rem; text-align: center;">
                <h3 style="color: var(--success); margin-bottom: 10px;"><i class="fas fa-info-circle"></i> ملاحظة هامة</h3>
                <p>هذا الموقع مرجعي فقط ولا يُغني عن الحكم السريري. جميع المعلومات مبنية على أحدث الأدلة العلمية المتاحة.</p>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>PedSafeDose</h3>
                    <p>مرجع موثوق لمعلومات الجرعات الدوائية للأطفال من الولادة حتى 12 سنة، مصمم خصيصًا لمقدمي الرعاية الصحية.</p>
                </div>
                <div class="footer-column">
                    <h3>روابط سريعة</h3>
                    <ul>
                        <li><a href="#">الرئيسية</a></li>
                        <li><a href="#age-groups">الجرعات حسب العمر</a></li>
                        <li><a href="#warnings">تحذيرات حرجة</a></li>
                        <li><a href="#references">المراجع</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>المصادر</h3>
                    <ul>
                        <li><a href="#">BNF for Children</a></li>
                        <li><a href="#">UpToDate</a></li>
                        <li><a href="#">FDA Guidelines</a></li>
                        <li><a href="#">EMA Resources</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>تواصل معنا</h3>
                    <ul>
                        <li><i class="fas fa-envelope"></i> info@pedsafedose.com</li>
                        <li><i class="fas fa-phone"></i> +966 11 123 4567</li>
                        <li><i class="fas fa-map-marker-alt"></i> الرياض، المملكة العربية السعودية</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2026 PedSafeDose. جميع الحقوق محفوظة. تم إعداد هذا الدليل من قبل صيادلة مرخصين.</p>
            </div>
        </div>
    </footer>

    <script>
        // Database of medications with detailed information
        const medications = [
            {
                name: "NEBULIZER WITH PULMICORT",
                scientificName: "Budesonide",
                ageGroup: "6+ months",
                dosage: "0.25-0.5 mg مرتين يوميًا",
                indication: "الربو",
                warnings: "غير موصى به قبل 6 أشهر. قد يسبب تأخر النمو.",
                references: "BNF for Children, FDA"
            },
            {
                name: "Airfast 5 mg chewable tablet",
                scientificName: "Montelukast",
                ageGroup: "6+ years",
                dosage: "4 mg يوميًا (لمن هم دون 6 سنوات)",
                indication: "الربو والحساسية",
                warnings: "غير موصى به للرضع. قد يسبب أفكار انتحارية.",
                references: "FDA, EMA"
            },
            {
                name: "RYALTRIS",
                scientificName: "Olopatadine/Mometasone",
                ageGroup: "2+ years",
                dosage: "رشتان في كل فتحة أنف مرتين يوميًا",
                indication: "التهاب الأنف التحسسي",
                warnings: "غير موصى به قبل سنتين. قد يسبب نزيف أنفي.",
                references: "FDA, BNF"
            },
            {
                name: "Zoron 8 Mg 10 Tablet",
                scientificName: "Ondansetron",
                ageGroup: "4+ years",
                dosage: "4 مغ 30 دقيقة قبل العلاج الكيميائي، ثم 4 و8 ساعات بعد الجرعة الأولى، ثم كل 8 ساعات لمدة 1-2 أيام",
                indication: "الغثيان والقيء الناتج عن العلاج الكيميائي",
                warnings: "السلامة والفعالية غير مثبتة للأطفال دون 4 سنوات",
                references: "FDA Guidelines"
            },
            {
                name: "Ambolar",
                scientificName: "Ambroxol",
                ageGroup: "2+ years",
                dosage: "2.5 مل شراب ثلاث مرات يوميًا (2-5 سنوات)، 5 مل مرتين إلى ثلاث مرات يوميًا (6-12 سنة)",
                indication: "مذيب للبلغم للسعال",
                warnings: "غير موصى به قبل سنتين. خطر ردود الفعل التحسسية الشديدة.",
                references: "Manufacturer Guidelines"
            },
            {
                name: "KLACID XL 500MG 7 TAB",
                scientificName: "Clarithromycin",
                ageGroup: "12+ years",
                dosage: "500 mg مرتين يوميًا",
                indication: "العدوى البكتيرية",
                warnings: "غير موصى به قبل 12 سنة. قد يسبب اضطرابات قلبية.",
                references: "FDA, BNF"
            },
            {
                name: "Azimac 500 Mg 3 Blister",
                scientificName: "Azithromycin",
                ageGroup: "6+ months",
                dosage: "10 مغ/كغ يوميًا لمدة 3 أيام",
                indication: "العدوى البكتيرية",
                warnings: "تجنب في حديثي الولادة (خطر تضيق البواب).",
                references: "FDA Black Box Warning"
            },
            {
                name: "FLIXOTIDE 125 MCG EVOHALER",
                scientificName: "Fluticasone",
                ageGroup: "4+ years",
                dosage: "125-250 mcg مرتين يوميًا",
                indication: "الربو",
                warnings: "غير موصى به قبل 4 سنوات. قد يسبب تأخر النمو.",
                references: "BNF for Children"
            },
            {
                name: "Polmena",
                scientificName: "Budesonide",
                ageGroup: "3+ months",
                dosage: "0.5-1 مغ مرتين يوميًا (3 أشهر - 12 سنة)",
                indication: "الربو القصبي",
                warnings: "غير موصى به قبل 3 أشهر. خطر متلازمة كوشينغ الجهازية.",
                references: "Manufacturer Guidelines"
            },
            {
                name: "Decozal 0.05% Nasal Drops",
                scientificName: "Xylometazoline",
                ageGroup: "2+ years",
                dosage: "1-2 قطرة في كل فتحة أنف مرتين يوميًا",
                indication: "احتقان الأنف",
                warnings: "غير موصى به قبل سنتين. الاستخدام الطويل قد يسبب ارتداد الاحتقان.",
                references: "EMA Guidelines"
            },
            {
                name: "Ferose - F Tablet",
                scientificName: "Iron/Folic Acid",
                ageGroup: "Adults",
                dosage: "قرص واحد يوميًا",
                indication: "فقر الدم",
                warnings: "غير مناسب للرضع. جرعة زائدة قد تكون سامة.",
                references: "BNF for Children"
            },
            {
                name: "Fenistil Drops 0.1g-100ml",
                scientificName: "Dimetindene",
                ageGroup: "1+ month",
                dosage: "3-10 قطرات ثلاث مرات يوميًا (1-12 شهر)، 10-15 قطرة ثلاث مرات يوميًا (1-3 سنوات)، 15-20 قطرة ثلاث مرات يوميًا (3+ سنوات)",
                indication: "مضاد للحكة والحساسية",
                warnings: "غير موصى به لحديثي الولادة. خطر انقطاع النفس أثناء النوم.",
                references: "EMA, Lexicomp"
            },
            {
                name: "ROXONIN TAPE 100 mg Cutaneous Patch",
                scientificName: "Lornoxicam",
                ageGroup: "Adults",
                dosage: "لصقة واحدة يوميًا",
                indication: "الألم والالتهاب",
                warnings: "خطر السمية الكلوية. غير موصى به للأطفال.",
                references: "AHA, UpToDate"
            },
            {
                name: "TACROZ 0.03% 10gm OINTMENT",
                scientificName: "Tacrolimus",
                ageGroup: "2+ years",
                dosage: "طبقتين رقيقتين مرتين يوميًا",
                indication: "الأكزيما",
                warnings: "غير موصى به قبل سنتين. قد يزيد خطر العدوى.",
                references: "FDA, BNF"
            },
            {
                name: "Elica 0.1% Cream",
                scientificName: "Mometasone",
                ageGroup: "2+ years",
                dosage: "طبقتين رقيقتين مرة يوميًا",
                indication: "الأكزيما والتهاب الجلد",
                warnings: "خطر متلازمة كوشينغ الجهازية. تجنب الاستخدام المطول.",
                references: "FDA, BNF"
            }
        ];

        // Age navigation functionality
        const ageButtons = document.querySelectorAll('.age-btn');
        ageButtons.forEach(button => {
            button.addEventListener('click', () => {
                // Remove active class from all buttons
                ageButtons.forEach(btn => btn.classList.remove('active'));
                
                // Add active class to clicked button
                button.classList.add('active');
                
                // Hide all age content sections
                const ageContents = document.querySelectorAll('.age-content');
                ageContents.forEach(content => content.classList.remove('active'));
                
                // Show the selected age content
                const age = button.getAttribute('data-age');
                const selectedContent = document.getElementById(`age-${age}`);
                if (selectedContent) {
                    selectedContent.classList.add('active');
                }
            });
        });

        // Function to search medications
        function searchMedications(query) {
            if (!query.trim()) {
                return;
            }
            
            const searchTerm = query.toLowerCase();
            const results = medications.filter(med => 
                med.name.toLowerCase().includes(searchTerm) || 
                med.scientificName.toLowerCase().includes(searchTerm)
            );
            
            // If results found, show the first relevant age group
            if (results.length > 0) {
                // Get the minimum age from results
                let minAge = 144; // 12 years in months
                results.forEach(med => {
                    // Extract age from ageGroup string (e.g., "6+ months" -> 6)
                    const ageMatch = med.ageGroup.match(/(\d+)/);
                    if (ageMatch) {
                        const ageNum = parseInt(ageMatch[1]);
                        // Convert years to months if needed
                        let ageInMonths = ageNum;
                        if (med.ageGroup.includes('year')) {
                            ageInMonths = ageNum * 12;
                        } else if (med.ageGroup.includes('month')) {
                            // Already in months
                        } else if (med.ageGroup.includes('+')) {
                            // Handle cases like "3+ months"
                            ageInMonths = ageNum;
                        }
                        if (ageInMonths < minAge) {
                            minAge = ageInMonths;
                        }
                    }
                });
                
                // Activate the age button and content
                ageButtons.forEach(btn => {
                    if (parseInt(btn.getAttribute('data-age')) === minAge) {
                        btn.click();
                    }
                });
                
                // Scroll to the age content section
                const ageSection = document.querySelector('#age-groups');
                if (ageSection) {
                    ageSection.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            } else {
                alert('لم يتم العثور على نتائج. تأكد من كتابة اسم الدواء بشكل صحيح.');
            }
        }

        // Event listeners for search
        const searchInput = document.getElementById('drug-search');
        const searchButton = document.getElementById('search-btn');
        
        searchButton.addEventListener('click', () => {
            searchMedications(searchInput.value);
        });
        
        searchInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                searchMedications(searchInput.value);
            }
        });
        
        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Form submission handling
        const contactForm = document.querySelector('.contact-form');
        if(contactForm) {
            contactForm.addEventListener('submit', function(e) {
                e.preventDefault();
                alert('تم إرسال رسالتك بنجاح! سنقوم بالرد عليك في أقرب وقت ممكن.');
                this.reset();
            });
        }
    </script>
</body>
</html>

