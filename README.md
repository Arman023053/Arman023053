<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>নিউ নানা হোটেল উপস্থিতি ও বিলিং সিস্টেম</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Kalpurush', 'SolaimanLipi', Arial, sans-serif;
            line-height: 1.6;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: #333;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            margin-bottom: 30px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
        }
        
        .header h1 {
            color: #2c3e50;
            font-size: 2.5em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }
        
        .nav-tabs {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin: 20px 0;
            flex-wrap: wrap;
        }
        
        .nav-tab {
            background: #3498db;
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.3s ease;
            font-weight: 600;
        }
        
        .nav-tab:hover {
            background: #2980b9;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(52, 152, 219, 0.4);
        }
        
        .nav-tab.active {
            background: #27ae60;
            box-shadow: 0 4px 12px rgba(39, 174, 96, 0.4);
        }
        
        .tab-content {
            display: none;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }
        
        .tab-content.active {
            display: block;
            animation: fadeIn 0.5s ease-in;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .card {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin: 20px 0;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            border-left: 5px solid #3498db;
            transition: transform 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.15);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #2c3e50;
        }
        
        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 16px;
            transition: border-color 0.3s ease;
        }
        
        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #3498db;
            box-shadow: 0 0 10px rgba(52, 152, 219, 0.2);
        }
        
        .btn {
            background: linear-gradient(45deg, #3498db, #2980b9);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            transition: all 0.3s ease;
            margin: 5px;
        }
        
        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(52, 152, 219, 0.4);
        }
        
        .btn-success {
            background: linear-gradient(45deg, #27ae60, #229954);
        }
        
        .btn-danger {
            background: linear-gradient(45deg, #e74c3c, #c0392b);
        }
        
        .btn-warning {
            background: linear-gradient(45deg, #f39c12, #e67e22);
        }
        
        .table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }
        
        .table th,
        .table td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #e0e0e0;
        }
        
        .table th {
            background: linear-gradient(45deg, #34495e, #2c3e50);
            color: white;
            font-weight: 600;
        }
        
        .table tbody tr:hover {
            background: #f8f9fa;
        }
        
        .status-present {
            background: #27ae60;
            color: white;
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 12px;
            font-weight: 600;
        }
        
        .status-absent {
            background: #e74c3c;
            color: white;
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 12px;
            font-weight: 600;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 20px 0;
        }
        
        .stat-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 6px 25px rgba(0, 0, 0, 0.15);
        }
        
        .stat-number {
            font-size: 2.5em;
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        .milestone {
            background: #ecf0f1;
            border-left: 4px solid #3498db;
            padding: 15px;
            margin: 10px 0;
            border-radius: 0 10px 10px 0;
        }
        
        .milestone h4 {
            color: #2c3e50;
            margin-bottom: 8px;
        }
        
        .progress-bar {
            width: 100%;
            height: 20px;
            background: #ecf0f1;
            border-radius: 10px;
            overflow: hidden;
            margin: 10px 0;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(45deg, #27ae60, #2ecc71);
            transition: width 0.3s ease;
        }
        
        @media (max-width: 768px) {
            .nav-tabs {
                flex-direction: column;
                align-items: center;
            }
            
            .nav-tab {
                width: 200px;
                text-align: center;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .header h1 {
                font-size: 1.8em;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>নিউ নানা হোটেল</h1>
            <p>উপস্থিতি ও বিলিং ব্যবস্থাপনা সিস্টেম</p>
        </div>
        
        <div class="nav-tabs">
            <button class="nav-tab active" onclick="showTab('dashboard')">ড্যাশবোর্ড</button>
            <button class="nav-tab" onclick="showTab('students')">শিক্ষার্থী নিবন্ধন</button>
            <button class="nav-tab" onclick="showTab('attendance')">উপস্থিতি</button>
            <button class="nav-tab" onclick="showTab('billing')">বিলিং</button>
            <button class="nav-tab" onclick="showTab('reports')">রিপোর্ট</button>
            <button class="nav-tab" onclick="showTab('project')">প্রকল্প তথ্য</button>
        </div>
        
        <!-- Dashboard Tab -->
        <div id="dashboard" class="tab-content active">
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-number" id="totalStudents">45</div>
                    <div>মোট শিক্ষার্থী</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="presentToday">38</div>
                    <div>আজ উপস্থিত</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="monthlyRevenue">৳ 45,600</div>
                    <div>মাসিক আয়</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="pendingBills">7</div>
                    <div>অবিলিত</div>
                </div>
            </div>
            
            <div class="card">
                <h3>আজকের সারসংক্ষেপ</h3>
                <table class="table">
                    <thead>
                        <tr>
                            <th>সময়</th>
                            <th>কার্যক্রম</th>
                            <th>অবস্থা</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>৭:৩০ AM</td>
                            <td>সকালের নাস্তা পরিবেশন</td>
                            <td><span class="status-present">সম্পন্ন</span></td>
                        </tr>
                        <tr>
                            <td>১২:৩০ PM</td>
                            <td>দুপুরের খাবার</td>
                            <td><span class="status-present">চলমান</span></td>
                        </tr>
                        <tr>
                            <td>৮:০০ PM</td>
                            <td>রাতের খাবার</td>
                            <td><span class="status-absent">পেন্ডিং</span></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
        
        <!-- Students Tab -->
        <div id="students" class="tab-content">
            <div class="card">
                <h3>নতুন শিক্ষার্থী নিবন্ধন</h3>
                <form id="studentForm">
                    <div class="form-group">
                        <label>নাম *</label>
                        <input type="text" id="studentName" required>
                    </div>
                    <div class="form-group">
                        <label>শিক্ষার্থী আইডি *</label>
                        <input type="text" id="studentId" required>
                    </div>
                    <div class="form-group">
                        <label>মোবাইল নম্বর</label>
                        <input type="tel" id="studentPhone">
                    </div>
                    <div class="form-group">
                        <label>রুম নম্বর</label>
                        <input type="text" id="roomNumber">
                    </div>
                    <div class="form-group">
                        <label>মিল প্যাকেজ</label>
                        <select id="mealPackage">
                            <option value="full">পূর্ণ প্যাকেজ (৩ বেলা)</option>
                            <option value="lunch-dinner">দুপুর + রাত</option>
                            <option value="dinner-only">শুধু রাত</option>
                        </select>
                    </div>
                    <button type="submit" class="btn btn-success">নিবন্ধন করুন</button>
                </form>
            </div>
            
            <div class="card">
                <h3>নিবন্ধিত শিক্ষার্থীদের তালিকা</h3>
                <table class="table" id="studentsTable">
                    <thead>
                        <tr>
                            <th>আইডি</th>
                            <th>নাম</th>
                            <th>রুম</th>
                            <th>প্যাকেজ</th>
                            <th>অ্যাকশন</th>
                        </tr>
                    </thead>
                    <tbody id="studentsTableBody">
                        <!-- Dynamic content -->
                    </tbody>
                </table>
            </div>
        </div>
        
        <!-- Attendance Tab -->
        <div id="attendance" class="tab-content">
            <div class="card">
                <h3>উপস্থিতি রেকর্ড</h3>
                <div class="form-group">
                    <label>তারিখ নির্বাচন করুন</label>
                    <input type="date" id="attendanceDate" value="">
                </div>
                <button class="btn" onclick="loadAttendance()">উপস্থিতি লোড করুন</button>
                <button class="btn btn-success" onclick="syncZKTeco()">ZKTeco সিঙ্ক করুন</button>
            </div>
            
            <div class="card">
                <h3>আজকের উপস্থিতি</h3>
                <table class="table" id="attendanceTable">
                    <thead>
                        <tr>
                            <th>শিক্ষার্থী</th>
                            <th>সকালের নাস্তা</th>
                            <th>দুপুরের খাবার</th>
                            <th>রাতের খাবার</th>
                            <th>মোট</th>
                        </tr>
                    </thead>
                    <tbody id="attendanceTableBody">
                        <!-- Dynamic content -->
                    </tbody>
                </table>
            </div>
        </div>
        
        <!-- Billing Tab -->
        <div id="billing" class="tab-content">
            <div class="card">
                <h3>মাসিক বিল গণনা</h3>
                <div class="form-group">
                    <label>মাস ও বছর</label>
                    <input type="month" id="billingMonth">
                </div>
                <button class="btn" onclick="calculateBills()">বিল গণনা করুন</button>
                <button class="btn btn-warning" onclick="sendSMSReminders()">SMS রিমাইন্ডার পাঠান</button>
            </div>
            
            <div class="card">
                <h3>বিলিং সামারি</h3>
                <table class="table" id="billingTable">
                    <thead>
                        <tr>
                            <th>শিক্ষার্থী</th>
                            <th>উপস্থিতি</th>
                            <th>মিল চার্জ</th>
                            <th>অতিরিক্ত</th>
                            <th>মোট বিল</th>
                            <th>স্ট্যাটাস</th>
                        </tr>
                    </thead>
                    <tbody id="billingTableBody">
                        <!-- Dynamic content -->
                    </tbody>
                </table>
            </div>
        </div>
        
        <!-- Reports Tab -->
        <div id="reports" class="tab-content">
            <div class="card">
                <h3>রিপোর্ট জেনারেট করুন</h3>
                <div class="form-group">
                    <label>রিপোর্টের ধরন</label>
                    <select id="reportType">
                        <option value="monthly">মাসিক সামারি</option>
                        <option value="attendance">উপস্থিতি রিপোর্ট</option>
                        <option value="financial">আর্থিক রিপোর্ট</option>
                        <option value="student">শিক্ষার্থী রিপোর্ট</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>সময়কাল</label>
                    <input type="month" id="reportPeriod">
                </div>
                <button class="btn" onclick="generateReport()">রিপোর্ট তৈরি করুন</button>
                <button class="btn btn-success" onclick="exportReport()">এক্সপোর্ট (PDF)</button>
            </div>
        </div>
        
        <!-- Project Info Tab -->
        <div id="project" class="tab-content">
            <div class="card">
                <h2>প্রকল্প সম্পর্কে</h2>
                <p><strong>"নিউ নানা হোটেল"</strong> শিক্ষার্থীদের প্রতিদিনের খাবার সরবরাহ করে এমন একটি মেস/হোস্টেল হিসেবে কাজ করে। এই সিস্টেমটি শিক্ষার্থীদের উপস্থিতি ট্র্যাকিং এবং খাবারের বিল পরিচালনার জন্য ডিজাইন করা হয়েছে।</p>
            </div>
            
            <div class="card">
                <h3>প্রয়োজনীয়তা (Must Have)</h3>
                <ul>
                    <li><strong>শিক্ষার্থীদের তথ্য নিবন্ধন:</strong> ব্যক্তিগত তথ্য, রুম নম্বর, মিল প্যাকেজ</li>
                    <li><strong>ZKTeco ডিভাইস থেকে উপস্থিতি সংগ্রহ:</strong> বায়োমেট্রিক ডেটা ইন্টিগ্রেশন</li>
                    <li><strong>খাবারের বিল গণনা ও মিল চার্জ:</strong> উপস্থিতি ভিত্তিক বিলিং</li>
                    <li><strong>মাসিক রিপোর্ট ও এসএমএস ব্যবস্থা:</strong> স্বয়ংক্রিয় বিল পাঠানো</li>
                </ul>
            </div>
            
            <div class="card">
                <h3>প্রযুক্তিগত স্পেসিফিকেশন</h3>
                <ul>
                    <li><strong>Backend:</strong> Node.js with Express</li>
                    <li><strong>Frontend:</strong> Flutter (Mobile App)</li>
                    <li><strong>Database:</strong> PostgreSQL</li>
                    <li><strong>Integration:</strong> ZKTeco API, SMS Gateway</li>
                    <li><strong>Hosting:</strong> Cloud-based deployment</li>
                </ul>
            </div>
            
            <div class="card">
                <h3>প্রকল্পের মাইলস্টোন</h3>
                <div class="milestone">
                    <h4>সপ্তাহ ১: চাহিদা চূড়ান্তকরণ ও সেটআপ</h4>
                    <p>সিস্টেম আর্কিটেকচার ডিজাইন, ডেটাবেস স্কিমা প্রস্তুতি</p>
                    <div class="progress-bar">
                        <div class="progress-fill" style="width: 100%"></div>
                    </div>
                </div>
                
                <div class="milestone">
                    <h4>সপ্তাহ ২-৩: মূল মডিউল ডেভেলপমেন্ট</h4>
                    <p>শিক্ষার্থী নিবন্ধন, উপস্থিতি ট্র্যাকিং, বিলিং সিস্টেম</p>
                    <div class="progress-bar">
                        <div class="progress-fill" style="width: 75%"></div>
                    </div>
                </div>
                
                <div class="milestone">
                    <h4>সপ্তাহ ৪-৫: রিপোর্টিং ও ডিপ্লয়মেন্ট</h4>
                    <p>রিপোর্ট জেনারেশন, SMS ইন্টিগ্রেশন, প্রোডাকশন ডিপ্লয়মেন্ট</p>
                    <div class="progress-bar">
                        <div class="progress-fill" style="width: 40%"></div>
                    </div>
                </div>
            </div>
            
            <div class="card">
                <h3>সফলতার মেট্রিকস</h3>
                <ul>
                    <li><strong>সঠিকতা যাচাই:</strong> ৯৮% উপস্থিতি ডেটা নির্ভুলতা</li>
                    <li><strong>এসএমএস সফলতা:</strong> ৯৫% ডেলিভারি রেট</li>
                    <li><strong>অ্যাডমিন ফিডব্যাক:</strong> ৪.৫/৫ সন্তুষ্টির হার</li>
                    <li><strong>সময় সাশ্রয়:</strong> ৭০% ম্যানুয়াল কাজ হ্রাস</li>
                </ul>
            </div>
        </div>
    </div>
    
    <script>
        // Sample data storage (in real app, this would be handled by backend)
        let students = [
            {id: 'S001', name: 'আহমেদ আলী', room: '101', package: 'full'},
            {id: 'S002', name: 'ফাতিমা খান', room: '102', package: 'lunch-dinner'},
            {id: 'S003', name: 'মোঃ রহিম', room: '103', package: 'full'},
            {id: 'S004', name: 'সারা বেগম', room: '104', package: 'dinner-only'}
        ];
        
        let attendance = {};
        let billing = {};
        
        // Initialize
        document.addEventListener('DOMContentLoaded', function() {
            document.getElementById('attendanceDate').value = new Date().toISOString().split('T')[0];
            loadStudentsTable();
            loadAttendanceTable();
            loadBillingTable();
        });
        
        // Tab switching
        function showTab(tabName) {
            // Hide all tabs
            const tabs = document.querySelectorAll('.tab-content');
            tabs.forEach(tab => tab.classList.remove('active'));
            
            // Remove active class from nav tabs
            const navTabs = document.querySelectorAll('.nav-tab');
            navTabs.forEach(tab => tab.classList.remove('active'));
            
            // Show selected tab
            document.getElementById(tabName).classList.add('active');
            event.target.classList.add('active');
        }
        
        // Student registration
        document.getElementById('studentForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const student = {
                id: document.getElementById('studentId').value,
                name: document.getElementById('studentName').value,
                phone: document.getElementById('studentPhone').value,
                room: document.getElementById('roomNumber').value,
                package: document.getElementById('mealPackage').value
            };
            
            students.push(student);
            loadStudentsTable();
            this.reset();
            alert('শিক্ষার্থী সফলভাবে নিবন্ধিত হয়েছে!');
        });
        
        function loadStudentsTable() {
            const tbody = document.getElementById('studentsTableBody');
            tbody.innerHTML = '';
            
            students.forEach(student => {
                const row = `
                    <tr>
                        <td>${student.id}</td>
                        <td>${student.name}</td>
                        <td>${student.room}</td>
                        <td>${getPackageName(student.package)}</td>
                        <td>
                            <button class="btn btn-warning" onclick="editStudent('${student.id}')">সম্পাদনা</button>
                            <button class="btn btn-danger" onclick="deleteStudent('${student.id}')">মুছুন</button>
                        </td>
                    </tr>
                `;
                tbody.innerHTML += row;
            });
        }
        
        function getPackageName(package) {
            const packages = {
                'full': 'পূর্ণ প্যাকেজ',
                'lunch-dinner': 'দুপুর + রাত',
                'dinner-only': 'শুধু রাত'
            };
            return packages[package] || package;
        }
        
        function editStudent(id) {
            alert('সম্পাদনা ফিচার শীঘ্রই আসছে!');
        }
        
        function deleteStudent(id) {
            if (confirm('আপনি কি নিশ্চিত যে এই শিক্ষার্থীকে মুছে ফেলতে চান?')) {
                students = students.filter(s => s.id !== id);
                loadStudentsTable();
                alert('শিক্ষার্থী মুছে ফেলা হয়েছে!');
            }
        }
        
        function loadAttendance() {
            // Simulate loading attendance data
            loadAttendanceTable();
            alert('উপস্থিতি ডেটা লোড করা হয়েছে!');
        }
        
        function syncZKTeco() {
            // Simulate ZKTeco sync
            alert('ZKTeco ডিভাইসের সাথে সিঙ্ক করা হচ্ছে...');
            setTimeout(() => {
                alert('ZKTeco সিঙ্ক সম্পন্ন!');
                loadAttendanceTable();
            }, 2000);
        }
        
        function loadAttendanceTable() {
            const tbody = document.getElementById('attendanceTableBody');
            tbody.innerHTML = '';
            
            students.forEach(student => {
                const breakfast = Math.random() > 0.2;
                const lunch = Math.random() > 0.15;
                const dinner = Math.random() > 0.1;
                const total = (breakfast ? 1 : 0) + (lunch ? 1 : 0) + (dinner ? 1 : 0);
                
                const row = `
                    <tr>
                        <td>${student.name}</td>
                        <td><span class="status-${breakfast ? 'present' : 'absent'}">${breakfast ? 'উপস
