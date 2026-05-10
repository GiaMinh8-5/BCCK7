[MinhEdu_Nhatkyhoctap.html](https://github.com/user-attachments/files/27561104/MinhEdu_Nhatkyhoctap.html)
# BC[MinhEdu_MuaKhoaHoc.html](https://github.com/user-attachments/files/27561108/MinhEdu_MuaKhoaHoc.html)
[MinhEdu_Doiqua.html](https://github.com/user-attachments/files/27561107/MinhEdu_Doiqua.html)
[MinhEdu_Vaohoc.html](https://github.com/user-attachments/files/27561106/MinhEdu_Vaohoc.html)
[MinhEdu_ThanhTich.html](https://github.com/user-attachments/files/27561105/MinhEdu_ThanhTich.html)
CK7
MinhEdu!
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MinhEdu - Học tập chủ động</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #d4e815;
            --primary-dark: #b8cc00;
            --primary-light: #f1f8a4;
            --dark: #1a1a2e;
            --mid: #333;
            --bg: #f5f7f0;
            --white: #ffffff;
            --danger: #e53935;
            --success: #43a047;
            --info: #039be5;
            --radius: 16px;
            --shadow: 0 8px 32px rgba(0,0,0,0.10);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }

        body {
            font-family: 'Nunito', sans-serif;
            background: var(--bg);
            min-height: 100vh;
        }

        /* ===== PAGE SYSTEM ===== */
        .page { display: none; }
        .page.active { display: block; }

        /* ===== AUTH PAGES ===== */
        .auth-page {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 20px;
        }

        .auth-box {
            background: white;
            border-radius: 24px;
            padding: 44px 40px;
            width: 100%;
            max-width: 420px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.25);
            animation: slideIn 0.4s ease-out;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(-24px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .auth-logo {
            text-align: center;
            margin-bottom: 28px;
        }

        .auth-logo h1 {
            font-size: 36px;
            font-weight: 900;
            color: var(--primary);
            letter-spacing: -1px;
            text-shadow: 2px 3px 0 #c4d800;
        }

        .auth-logo p {
            color: #888;
            font-size: 15px;
            margin-top: 4px;
        }

        .form-field {
            margin-bottom: 18px;
        }

        .form-field label {
            display: block;
            margin-bottom: 7px;
            font-weight: 700;
            font-size: 14px;
            color: #444;
        }

        .form-field input {
            width: 100%;
            padding: 13px 16px;
            border: 2px solid #e5e5e5;
            border-radius: 12px;
            font-size: 15px;
            font-family: inherit;
            transition: 0.2s;
            background: #fafafa;
            color: #222;
        }

        .form-field input:focus {
            outline: none;
            border-color: var(--primary);
            background: white;
            box-shadow: 0 0 0 4px rgba(212,232,21,0.15);
        }

        .err-msg {
            display: block;
            color: var(--danger);
            font-size: 12px;
            font-weight: 600;
            margin-top: 5px;
            min-height: 16px;
        }

        .btn-primary-auth {
            width: 100%;
            padding: 14px;
            background: var(--primary);
            color: #222;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 800;
            cursor: pointer;
            transition: 0.2s;
            margin-top: 6px;
            letter-spacing: 0.3px;
        }

        .btn-primary-auth:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(180,210,0,0.35);
        }

        .auth-footer {
            text-align: center;
            margin-top: 22px;
            padding-top: 20px;
            border-top: 1px solid #eee;
        }

        .auth-footer p { color: #777; font-size: 14px; margin-bottom: 8px; }

        .auth-footer a {
            color: #764ba2;
            font-weight: 700;
            text-decoration: none;
            cursor: pointer;
        }

        .auth-footer a:hover { text-decoration: underline; }

        /* ===== MAIN APP ===== */
        #page-main { display: none; flex-direction: column; min-height: 100vh; }
        #page-main.active { display: flex; }

        .header-top {
            background: white;
            padding: 12px 0;
            border-bottom: 1px solid #eee;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        }

        .search-box {
            border: 1.5px solid #ddd;
            border-radius: 50px;
            padding: 7px 16px;
            display: flex;
            align-items: center;
            max-width: 280px;
            background: #fafafa;
        }

        .search-box input {
            border: none;
            outline: none;
            background: transparent;
            width: 100%;
            margin-left: 8px;
            font-size: 14px;
            font-family: inherit;
        }

        .user-chip {
            display: flex;
            align-items: center;
            gap: 8px;
            background: var(--primary-light);
            border: 1.5px solid var(--primary);
            border-radius: 50px;
            padding: 6px 16px 6px 10px;
            font-weight: 700;
            font-size: 14px;
            color: #333;
        }

        .user-chip .avatar {
            width: 28px; height: 28px;
            background: var(--primary);
            border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            font-weight: 900; font-size: 13px;
        }

        .btn-logout {
            background: #f0f0f0;
            border: none;
            border-radius: 50px;
            padding: 7px 18px;
            font-size: 13px;
            font-weight: 700;
            cursor: pointer;
            color: #555;
            transition: 0.2s;
        }

        .btn-logout:hover { background: #e0e0e0; color: #333; }

        .navbar-custom {
            background: var(--dark);
            padding: 0;
            overflow-x: auto;
        }

        .navbar-custom::-webkit-scrollbar { height: 3px; }
        .navbar-custom::-webkit-scrollbar-thumb { background: var(--primary); }

        .navbar-nav-custom {
            display: flex;
            white-space: nowrap;
            padding: 0 16px;
        }

        .navbar-nav-custom a {
            color: rgba(255,255,255,0.75) !important;
            font-weight: 700;
            padding: 13px 18px !important;
            text-transform: uppercase;
            font-size: 12px;
            letter-spacing: 0.5px;
            text-decoration: none;
            display: inline-block;
            transition: 0.2s;
            border-bottom: 3px solid transparent;
        }

        .navbar-nav-custom a:hover,
        .navbar-nav-custom a.active {
            color: var(--primary) !important;
            border-bottom-color: var(--primary);
        }

        /* Subject cards */
        .subject-card {
            background: white;
            border-radius: 14px;
            padding: 14px 20px;
            text-align: center;
            border: 2px solid #eee;
            cursor: pointer;
            transition: 0.2s;
            min-width: 110px;
        }

        .subject-card:hover { border-color: var(--primary); box-shadow: 0 4px 12px rgba(0,0,0,0.08); }
        .subject-card.active { border-color: var(--dark); background: var(--primary-light); }
        .subject-icon { width: 38px; margin-bottom: 8px; }

        /* Sidebar */
        .sidebar-title {
            background: var(--dark);
            color: var(--primary);
            padding: 14px 18px;
            border-radius: 14px 14px 0 0;
            font-weight: 800;
            font-size: 14px;
            letter-spacing: 0.3px;
        }

        .lesson-container {
            background: white;
            border-radius: 0 0 14px 14px;
            padding: 14px;
            min-height: 380px;
            box-shadow: var(--shadow);
        }

        .lesson-item {
            background: #f9f9f9;
            border: 1.5px solid #eee;
            border-radius: 12px;
            padding: 12px 14px;
            margin-bottom: 10px;
            cursor: pointer;
            transition: 0.2s;
        }

        .lesson-item:hover { border-color: var(--primary); }
        .lesson-item.highlight { background: var(--primary-light); border-color: var(--primary); }

        /* Topic & cards */
        .topic-header {
            background: white;
            border-radius: 14px;
            padding: 20px;
            border: 1.5px solid #eee;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
        }

        .grid-card {
            background: linear-gradient(135deg, #ffe082 0%, #ffca28 100%);
            border-radius: 16px;
            padding: 28px 20px;
            cursor: pointer;
            transition: 0.25s;
            box-shadow: 0 4px 16px rgba(255,200,0,0.2);
            border: 2px solid transparent;
            height: 100%;
        }

        .grid-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 12px 32px rgba(255,180,0,0.3);
            border-color: var(--primary-dark);
        }

        .grid-card .card-title {
            font-weight: 800;
            font-size: 16px;
            color: #333;
            margin-bottom: 6px;
        }

        .grid-card .card-sub {
            font-size: 13px;
            color: #666;
        }

        .grid-card .card-icon {
            font-size: 28px;
            margin-bottom: 10px;
        }

        /* ===== QUIZ PAGE ===== */
        .quiz-page {
            min-height: 100vh;
            background: linear-gradient(160deg, #1a1a2e 0%, #16213e 60%, #0f3460 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 24px;
        }

        .quiz-box {
            width: 100%;
            max-width: 680px;
            background: white;
            border-radius: 24px;
            padding: 40px;
            box-shadow: 0 24px 80px rgba(0,0,0,0.4);
            animation: slideIn 0.4s ease-out;
        }

        .quiz-header-bar {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 24px;
        }

        .quiz-logo {
            font-size: 22px;
            font-weight: 900;
            color: var(--primary);
            letter-spacing: -0.5px;
        }

        .q-counter {
            background: var(--primary-light);
            border: 1.5px solid var(--primary);
            border-radius: 50px;
            padding: 5px 16px;
            font-size: 13px;
            font-weight: 800;
            color: #444;
        }

        .progress-track {
            height: 8px;
            background: #f0f0f0;
            border-radius: 99px;
            margin-bottom: 28px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary-dark), var(--primary));
            border-radius: 99px;
            transition: width 0.4s ease;
        }

        .question-text {
            font-size: 20px;
            font-weight: 800;
            color: #1a1a2e;
            margin-bottom: 24px;
            line-height: 1.45;
        }

        .question-num {
            font-size: 12px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: #aaa;
            margin-bottom: 8px;
        }

        .option-btn {
            display: block;
            width: 100%;
            text-align: left;
            padding: 15px 20px;
            border: 2px solid #e8e8e8;
            border-radius: 12px;
            background: #fafafa;
            font-size: 15px;
            font-weight: 600;
            font-family: inherit;
            color: #333;
            cursor: pointer;
            margin-bottom: 12px;
            transition: 0.18s;
            position: relative;
        }

        .option-btn:hover:not(:disabled) {
            border-color: var(--primary);
            background: var(--primary-light);
            transform: translateX(4px);
        }

        .option-btn.selected {
            border-color: var(--primary);
            background: var(--primary-light);
        }

        .option-btn.correct {
            border-color: var(--success) !important;
            background: #e8f5e9 !important;
            color: #1b5e20 !important;
        }

        .option-btn.correct::after {
            content: ' ✓';
            font-weight: 900;
            color: var(--success);
        }

        .option-btn.incorrect {
            border-color: var(--danger) !important;
            background: #ffebee !important;
            color: #b71c1c !important;
        }

        .option-btn.incorrect::after {
            content: ' ✗';
            font-weight: 900;
            color: var(--danger);
        }

        .option-btn:disabled { cursor: default; }

        .feedback-box {
            margin-top: 16px;
            padding: 14px 18px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 15px;
            display: none;
        }

        .feedback-box.show { display: block; animation: feedbackIn 0.3s ease; }

        @keyframes feedbackIn {
            from { opacity: 0; transform: scale(0.96); }
            to { opacity: 1; transform: scale(1); }
        }

        .feedback-box.correct-fb {
            background: #e8f5e9;
            color: #1b5e20;
            border: 1.5px solid #81c784;
        }

        .feedback-box.incorrect-fb {
            background: #ffebee;
            color: #b71c1c;
            border: 1.5px solid #e57373;
        }

        .btn-next-q {
            width: 100%;
            padding: 14px;
            background: var(--dark);
            color: var(--primary);
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 20px;
            transition: 0.2s;
            letter-spacing: 0.3px;
        }

        .btn-next-q:hover { background: #2d2d50; transform: translateY(-2px); }
        .btn-next-q:disabled { background: #ccc; color: #888; cursor: not-allowed; transform: none; }

        /* Result */
        .result-screen { text-align: center; padding: 20px 0; }
        .score-circle {
            width: 140px; height: 140px;
            border-radius: 50%;
            background: conic-gradient(var(--primary) var(--pct, 0%), #f0f0f0 0%);
            display: flex; align-items: center; justify-content: center;
            margin: 0 auto 20px;
            position: relative;
            box-shadow: 0 8px 32px rgba(180,210,0,0.25);
        }

        .score-circle-inner {
            width: 112px; height: 112px;
            background: white;
            border-radius: 50%;
            display: flex; flex-direction: column;
            align-items: center; justify-content: center;
        }

        .score-num {
            font-size: 32px;
            font-weight: 900;
            color: var(--dark);
            line-height: 1;
        }

        .score-total { font-size: 13px; color: #aaa; font-weight: 700; }

        .result-emoji { font-size: 48px; margin-bottom: 10px; }
        .result-msg { font-size: 20px; font-weight: 800; color: #333; }
        .result-sub { font-size: 15px; color: #888; margin-top: 8px; }

        .btn-retry {
            display: inline-block;
            padding: 12px 32px;
            background: var(--primary);
            color: #333;
            border: none;
            border-radius: 50px;
            font-size: 15px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 24px;
            margin-right: 10px;
            transition: 0.2s;
        }

        .btn-retry:hover { background: var(--primary-dark); transform: translateY(-2px); }

        .btn-home {
            display: inline-block;
            padding: 12px 32px;
            background: var(--dark);
            color: var(--primary);
            border: none;
            border-radius: 50px;
            font-size: 15px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 24px;
            transition: 0.2s;
        }

        .btn-home:hover { background: #2d2d50; transform: translateY(-2px); }

        /* Toast */
        .toast-msg {
            position: fixed;
            top: 20px; right: 20px;
            background: #222;
            color: #fff;
            padding: 14px 22px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 14px;
            z-index: 9999;
            transform: translateX(200px);
            opacity: 0;
            transition: 0.3s;
            max-width: 300px;
        }

        .toast-msg.show { transform: translateX(0); opacity: 1; }
        .toast-msg.success { border-left: 4px solid var(--primary); }
        .toast-msg.error { border-left: 4px solid var(--danger); }

        @media (max-width: 600px) {
            .auth-box, .quiz-box { padding: 28px 20px; }
            .question-text { font-size: 17px; }
        }
        .math-bg {
    position: fixed;
    inset: 0;
    overflow: hidden;
    z-index: -1;
}

.math-bg span {
    position: absolute;
    color: rgba(0,0,0,0.1);
    font-weight: bold;
    animation: float 10s linear infinite;
    text-shadow: 
        0 0 2px rgba(0,0,0,0.3),
        0 0 6px rgba(0,0,0,0.2);
}

@keyframes float {
    from {
        transform: translateY(100vh);
        opacity: 1;
    }
    to {
        transform: translateY(-10vh);
        opacity: 1;
    }
}
    </style>
</head>
<body>
<div class="math-bg"></div>
<!-- TOAST -->
<div class="toast-msg" id="toast"></div>

<!-- ===== PAGE: ĐĂNG NHẬP ===== -->
<div id="page-login" class="page active">
    <div class="auth-page">
        <div class="auth-box">
            <div class="auth-logo">
                <h1>MinhEdu</h1>
                <p>Đăng nhập vào tài khoản của bạn</p>
            </div>
            <div class="form-field">
                <label>Email</label>
                <input type="email" id="login-email" placeholder="Nhập email của bạn">
                <span class="err-msg" id="login-email-err"></span>
            </div>
            <div class="form-field">
                <label>Mật khẩu</label>
                <input type="password" id="login-password" placeholder="Nhập mật khẩu" onkeydown="if(event.key==='Enter') doLogin()">
                <span class="err-msg" id="login-pass-err"></span>
            </div>
            <button class="btn-primary-auth" onclick="doLogin()">Đăng nhập</button>
            <div class="auth-footer">
                <p>Chưa có tài khoản? <a onclick="showPage('page-register')">Đăng ký ngay</a></p>
                <a onclick="showPage('page-main')">← Vào xem trang chính</a>
            </div>
        </div>
    </div>
</div>

<!-- ===== PAGE: ĐĂNG KÝ ===== -->
<div id="page-register" class="page">
    <div class="auth-page">
        <div class="auth-box">
            <div class="auth-logo">
                <h1>MinhEdu</h1>
                <p>Tạo tài khoản mới</p>
            </div>
            <div class="form-field">
                <label>Họ và tên</label>
                <input type="text" id="reg-name" placeholder="Nguyễn Văn A">
                <span class="err-msg" id="reg-name-err"></span>
            </div>
            <div class="form-field">
                <label>Email</label>
                <input type="email" id="reg-email" placeholder="email@example.com">
                <span class="err-msg" id="reg-email-err"></span>
            </div>
            <div class="form-field">
                <label>Mật khẩu</label>
                <input type="password" id="reg-pass" placeholder="Tối thiểu 6 ký tự">
                <span class="err-msg" id="reg-pass-err"></span>
            </div>
            <div class="form-field">
                <label>Xác nhận mật khẩu</label>
                <input type="password" id="reg-confirm" placeholder="Nhập lại mật khẩu" onkeydown="if(event.key==='Enter') doRegister()">
                <span class="err-msg" id="reg-confirm-err"></span>
            </div>
            <button class="btn-primary-auth" onclick="doRegister()">Đăng ký</button>
            <div class="auth-footer">
                <p>Đã có tài khoản? <a onclick="showPage('page-login')">Đăng nhập</a></p>
                <a onclick="showPage('page-main')">← Vào xem trang chính</a>
            </div>
        </div>
    </div>
</div>

<!-- ===== PAGE: TRANG CHÍNH ===== -->
<div id="page-main" class="page">
    <header class="header-top">
        <div class="container d-flex justify-content-between align-items-center">
            <div class="d-flex align-items-center gap-3">
                <div style="font-weight:900;font-size:22px;color:var(--dark);letter-spacing:-0.5px;">MinhEdu</div>
                <div class="search-box">
                    <i class="fas fa-search" style="color:#bbb;font-size:13px;"></i>
                    <input type="text" placeholder="Tìm kiếm bài học...">
                </div>
            </div>
            <div class="d-flex align-items-center gap-2" id="header-auth-area">
                <button class="btn btn-dark rounded-pill px-4 fw-bold" style="font-size:14px;" onclick="showPage('page-login')">Đăng nhập</button>
                <button class="btn rounded-pill px-4 fw-bold" style="background:var(--primary);font-size:14px;" onclick="showPage('page-register')">Đăng ký</button>
            </div>
        </div>
    </header>

    <nav class="navbar-custom">
        <div class="container">
            <div class="navbar-nav-custom">
                <a href="MinhEdu_Vaohoc.html">Vào học</a>
                <a href="MinhEdu_Nhatkyhoctap.html"  class="active">Nhật ký học tập</a>
                <a href="MinhEdu_Doiqua.html">Đổi quà</a>
                <a href="MinhEdu_ThanhTich.html">Thành tích</a>
                <a href="MinhEdu_MuaKhoaHoc.html">Mua khóa học</a>
            </div>
        </div>
    </nav>

    <main class="container mt-4 pb-5">
        <div class="row g-4">
            <div class="col-md-12">
                <div class="d-flex justify-content-between align-items-center mb-3">
                    
                    <div class="d-flex gap-2">
                        <select class="form-select rounded-pill" style="font-size:13px;width:auto;">
                            <option>Lớp 8</option>
                            <option>Lớp 7</option>
                            <option>Lớp 9</option>
                        </select>
                        <select class="form-select rounded-pill" style="font-size:13px;width:auto;">
                            <option>Chân trời sáng tạo</option>
                            <option>Kết nối tri thức</option>
                        </select>
                    </div>
                </div>

                <div class="topic-header">
                    <div class="d-flex align-items-center justify-content-between">
                        <span class="fw-bold justify-content-between" id="topic-title">BÀI KIỂM TRA</span>
                        <span class="badge bg-light text-dark border fw-bold">0%</span>
                    </div>
                </div>

                <div class="row g-3">
                    <div class="col-sm-6">
                        <div class="grid-card" onclick="startQuiz('KIỂM TRA GIỮA KÌ I')">
                            <div class="card-icon">📐</div>
                            <div class="card-title">KIỂM TRA GIỮA KÌ I</div>
                            <div class="card-sub">5 câu hỏi · ~5 phút</div>
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="grid-card" onclick="startQuiz('KIỂM TRA GIỮA KÌ II')">
                            <div class="card-icon">📊</div>
                            <div class="card-title">KIỂM TRA GIỮA KÌ II</div>
                            <div class="card-sub">5 câu hỏi · ~5 phút</div>
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="grid-card" onclick="startQuiz('KIỂM TRA CUỐI KÌ I')">
                            <div class="card-icon">➕</div>
                            <div class="card-title">KIỂM TRA CUỐI KÌ I</div>
                            <div class="card-sub">4 câu hỏi · ~4 phút</div>
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="grid-card" onclick="startQuiz('KIỂM TRA CUỐI KỲ II')">
                            <div class="card-icon">⚡</div>
                            <div class="card-title">KIỂM TRA CUỐI KỲ II</div>
                            <div class="card-sub">5 câu hỏi · ~6 phút</div>
                        </div>
                    </div>
                </div>
                <div class="topic-header mt-3">
                    <div class="d-flex align-items-center justify-content-between">
                        <span class="fw-bold justify-content-between" id="topic-title">BÀI TẬP VỀ NHÀ</span>
                        <span class="badge bg-light text-dark border fw-bold">Hiện chưa có</span>
                    </div>
                </div>
            </div>
        </div>
    </main>
</div>

<!-- ===== PAGE: QUIZ ===== -->
<div id="page-quiz" class="page">
    <div class="quiz-page">
        <div class="quiz-box">
            <!-- Quiz header -->
            <div class="quiz-header-bar">
                <span class="quiz-logo">MinhEdu</span>
                <span class="q-counter" id="q-counter">1 / 5</span>
            </div>

            <!-- Progress -->
            <div class="progress-track">
                <div class="progress-fill" id="q-progress" style="width:0%;"></div>
            </div>

            <!-- Question area -->
            <div id="quiz-question-area">
                <div class="question-num" id="q-num">CÂU HỎI 1</div>
                <div class="question-text" id="q-text"></div>
                <div id="q-options"></div>
                <div class="feedback-box" id="q-feedback"></div>
                <button class="btn-next-q" id="btn-next" onclick="nextQuestion()" disabled>Câu tiếp theo →</button>
            </div>

            <!-- Result area (hidden) -->
            <div id="quiz-result-area" style="display:none;">
                <div class="result-screen">
                    <div class="score-circle" id="score-circle">
                        <div class="score-circle-inner">
                            <div class="score-num" id="result-score">0/5</div>
                            <div class="score-total" id="result-pct">0%</div>
                        </div>
                    </div>
                    <div class="result-emoji" id="result-emoji">🎉</div>
                    <div class="result-msg" id="result-msg">Xuất sắc!</div>
                    <div class="result-sub" id="result-sub">Bạn đã hoàn thành bài tập</div>
                    <div>
                        <button class="btn-retry" onclick="retryQuiz()">🔄 Làm lại</button>
                        <button class="btn-home" onclick="showPage('page-main')">🏠 Trang chủ</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

<script>
// ============================
// DATA
// ============================
const ALL_QUESTIONS = {
    'KIỂM TRA GIỮA KÌ I': [
        { q: "Cho tam giác ABC có AB, AC, BC lần lượt là: 3, 4, 5 (cm). Hỏi ABC là tam giác gì?", opts: ["Tam giác từ", "Tam giác nhọn", "Tam giác vuông", "Không tồn tại tam giác ấy"], ans: 2 },
        { q: "Bậc của đơn thức 3x²y³ là bao nhiêu?", opts: ["2", "3", "5", "6"], ans: 2 },
        { q: "Đơn thức nào sau đây có bậc là 4?", opts: ["5x³y", "2x²y²", "3xy", "7x⁴"], ans: 1 },
        { q: "Hệ số của đơn thức -7x²y là bao nhiêu?", opts: ["7", "-7", "2", "-2"], ans: 1 },
        { q: "Đơn thức đồng dạng với 3x²y là đơn thức nào?", opts: ["-5x²y", "3xy²", "3x²", "5xy"], ans: 0 }
    ],
    'KIỂM TRA GIỮA KÌ II': [
        { q: "Đa thức là gì?", opts: ["Tích của các đơn thức", "Tổng của các đơn thức", "Hiệu của các đơn thức", "Thương của các đơn thức"], ans: 1 },
        { q: "Bậc của đa thức 3x²y + 2xy³ - 5 là?", opts: ["2", "3", "4", "5"], ans: 2 },
        { q: "Đa thức x² + 2xy + y² có bao nhiêu hạng tử?", opts: ["1", "2", "3", "4"], ans: 2 },
        { q: "Thu gọn đa thức: 3x² + 2x - x² + 5 bằng?", opts: ["2x² + 2x + 5", "4x² + 2x + 5", "2x² - 2x + 5", "3x² + 2x + 5"], ans: 0 },
        { q: "Hạng tử tự do trong đa thức 2x² + 3x - 7 là?", opts: ["2", "3", "-7", "0"], ans: 2 }
    ],
    'KIỂM TRA CUỐI KÌ I': [
        { q: "2x + 3x bằng?", opts: ["5", "5x", "6x", "x"], ans: 1 },
        { q: "(2x + 3) - (x + 1) bằng?", opts: ["x + 2", "2x + 2", "3x + 4", "x - 2"], ans: 0 },
        { q: "(x² + 2x) + (3x² - x + 1) bằng?", opts: ["4x² + x + 1", "4x² + 3x + 1", "2x² + x + 1", "4x² - x + 1"], ans: 0 },
        { q: "Kết quả của (5x - 3) - (2x + 4) là?", opts: ["3x - 7", "3x + 1", "7x - 7", "3x - 1"], ans: 0 }
    ],
    'KIỂM TRA CUỐI KÌ II': [
        { q: "(a + b)² bằng?", opts: ["a² + b²", "a² + 2ab + b²", "a² - 2ab + b²", "a² + ab + b²"], ans: 1 },
        { q: "(a - b)² bằng?", opts: ["a² - b²", "a² + 2ab + b²", "a² - 2ab + b²", "a² - ab + b²"], ans: 2 },
        { q: "(a + b)(a - b) bằng?", opts: ["a² + b²", "a² - b²", "a² + 2ab - b²", "a² - 2ab + b²"], ans: 1 },
        { q: "(a + b)³ bằng?", opts: ["a³ + b³", "a³ + 3a²b + 3ab² + b³", "a³ - 3a²b + 3ab² - b³", "a³ + 3ab + b³"], ans: 1 },
        { q: "a³ - b³ bằng?", opts: ["(a-b)(a²+ab+b²)", "(a-b)(a²-ab+b²)", "(a+b)(a²-ab+b²)", "(a-b)³"], ans: 0 }
    ]
};

// ============================
// STATE
// ============================
let currentUser = null;
let quizState = {
    topic: '',
    questions: [],
    current: 0,
    score: 0,
    answered: false
};

// ============================
// INIT
// ============================
window.addEventListener('load', () => {
    const saved = localStorage.getItem('minhedu_user');
    if (saved) {
        currentUser = JSON.parse(saved);
        updateHeaderForUser();
        showPage('page-main');
    } else {
        showPage('page-login');
    }
});

// ============================
// PAGE NAV
// ============================
function showPage(id) {
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    window.scrollTo(0, 0);
}

// ============================
// AUTH
// ============================
function getUsers() {
    return JSON.parse(localStorage.getItem('minhedu_users') || '[]');
}

function saveUsers(users) {
    localStorage.setItem('minhedu_users', JSON.stringify(users));
}

function doLogin() {
    clearErrors(['login-email-err', 'login-pass-err']);
    const email = document.getElementById('login-email').value.trim();
    const pass = document.getElementById('login-password').value;

    let ok = true;
    if (!email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) {
        document.getElementById('login-email-err').textContent = 'Email không hợp lệ';
        ok = false;
    }
    if (pass.length < 6) {
        document.getElementById('login-pass-err').textContent = 'Mật khẩu phải ít nhất 6 ký tự';
        ok = false;
    }
    if (!ok) return;

    const users = getUsers();
    const user = users.find(u => u.email === email && u.password === pass);

    if (!user) {
        document.getElementById('login-pass-err').textContent = 'Email hoặc mật khẩu không chính xác';
        return;
    }

    currentUser = { id: user.id, name: user.name, email: user.email };
    localStorage.setItem('minhedu_user', JSON.stringify(currentUser));
    showToast('Chào mừng trở lại, ' + user.name + '! 👋', 'success');
    updateHeaderForUser();
    document.getElementById('login-email').value = '';
    document.getElementById('login-password').value = '';
    showPage('page-main');
}

function doRegister() {
    clearErrors(['reg-name-err', 'reg-email-err', 'reg-pass-err', 'reg-confirm-err']);
    const name = document.getElementById('reg-name').value.trim();
    const email = document.getElementById('reg-email').value.trim();
    const pass = document.getElementById('reg-pass').value;
    const confirm = document.getElementById('reg-confirm').value;

    let ok = true;
    if (name.length < 3) { document.getElementById('reg-name-err').textContent = 'Tên phải ít nhất 3 ký tự'; ok = false; }
    if (!email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) { document.getElementById('reg-email-err').textContent = 'Email không hợp lệ'; ok = false; }
    if (pass.length < 6) { document.getElementById('reg-pass-err').textContent = 'Mật khẩu phải ít nhất 6 ký tự'; ok = false; }
    if (pass !== confirm) { document.getElementById('reg-confirm-err').textContent = 'Mật khẩu không khớp'; ok = false; }
    if (!ok) return;

    const users = getUsers();
    if (users.find(u => u.email === email)) {
        document.getElementById('reg-email-err').textContent = 'Email đã được đăng ký!';
        return;
    }

    const newUser = { id: Date.now(), name, email, password: pass };
    users.push(newUser);
    saveUsers(users);

    currentUser = { id: newUser.id, name: newUser.name, email: newUser.email };
    localStorage.setItem('minhedu_user', JSON.stringify(currentUser));
    showToast('Đăng ký thành công! Chào mừng, ' + name + '! 🎉', 'success');
    updateHeaderForUser();
    document.getElementById('reg-name').value = '';
    document.getElementById('reg-email').value = '';
    document.getElementById('reg-pass').value = '';
    document.getElementById('reg-confirm').value = '';
    showPage('page-main');
}

function doLogout() {
    currentUser = null;
    localStorage.removeItem('minhedu_user');
    showToast('Đã đăng xuất', 'success');
    updateHeaderForUser();
}

function updateHeaderForUser() {
    const area = document.getElementById('header-auth-area');
    if (currentUser) {
        const initial = currentUser.name.charAt(0).toUpperCase();
        area.innerHTML = `
            <div class="user-chip">
                <div class="avatar">${initial}</div>
                <span>${currentUser.name}</span>
            </div>
            <button class="btn-logout" onclick="doLogout()">Đăng xuất</button>
        `;
    } else {
        area.innerHTML = `
            <button class="btn btn-dark rounded-pill px-4 fw-bold" style="font-size:14px;" onclick="showPage('page-login')">Đăng nhập</button>
            <button class="btn rounded-pill px-4 fw-bold" style="background:var(--primary);font-size:14px;" onclick="showPage('page-register')">Đăng ký</button>
        `;
    }
}

// ============================
// QUIZ
// ============================
function startQuiz(topic) {
    if (!currentUser) {
        showToast('Vui lòng đăng nhập để làm bài tập! 🔐', 'error');
        setTimeout(() => showPage('page-login'), 1200);
        return;
    }

    const qs = ALL_QUESTIONS[topic] || ALL_QUESTIONS['Đơn thức nhiều biến'];

    quizState = {
        topic,
        questions: shuffle([...qs]),
        current: 0,
        score: 0,
        answered: false
    };

    document.getElementById('quiz-question-area').style.display = 'block';
    document.getElementById('quiz-result-area').style.display = 'none';
    renderQuestion();
    showPage('page-quiz');
}

function renderQuestion() {
    const { questions, current } = quizState;
    const total = questions.length;
    const q = questions[current];

    document.getElementById('q-num').textContent = `CÂU HỎI ${current + 1}`;
    document.getElementById('q-counter').textContent = `${current + 1} / ${total}`;
    document.getElementById('q-text').textContent = q.q;
    document.getElementById('q-progress').style.width = ((current) / total * 100) + '%';

    const optContainer = document.getElementById('q-options');
    optContainer.innerHTML = q.opts.map((o, i) => `
        <button class="option-btn" onclick="selectAnswer(${i})" id="opt-${i}">${String.fromCharCode(65 + i)}. ${o}</button>
    `).join('');

    const fb = document.getElementById('q-feedback');
    fb.className = 'feedback-box';
    fb.innerHTML = '';

    document.getElementById('btn-next').disabled = true;
    document.getElementById('btn-next').textContent = current === total - 1 ? '🏁 Xem kết quả' : 'Câu tiếp theo →';
    quizState.answered = false;
}

function selectAnswer(idx) {
    if (quizState.answered) return;
    quizState.answered = true;

    const q = quizState.questions[quizState.current];
    const correct = q.ans;
    const opts = document.querySelectorAll('.option-btn');

    opts.forEach(b => b.disabled = true);
    opts.forEach((b, i) => {
        b.classList.remove('selected', 'correct', 'incorrect');
        if (i === correct) b.classList.add('correct');
        else if (i === idx) b.classList.add('incorrect');
    });

    const fb = document.getElementById('q-feedback');
    if (idx === correct) {
        quizState.score++;
        fb.className = 'feedback-box correct-fb show';
        fb.innerHTML = '✅ Chính xác! Bạn đã trả lời đúng.';
    } else {
        fb.className = 'feedback-box incorrect-fb show';
        fb.innerHTML = `❌ Sai rồi! Đáp án đúng là: <strong>${String.fromCharCode(65 + correct)}. ${q.opts[correct]}</strong>`;
    }

    document.getElementById('btn-next').disabled = false;
}

function nextQuestion() {
    if (!quizState.answered) {
        showToast('Hãy chọn một đáp án!', 'error');
        return;
    }
    quizState.current++;
    if (quizState.current < quizState.questions.length) {
        renderQuestion();
    } else {
        showResult();
    }
}

function showResult() {
    document.getElementById('quiz-question-area').style.display = 'none';
    document.getElementById('quiz-result-area').style.display = 'block';

    const { score, questions } = quizState;
    const total = questions.length;
    const pct = Math.round(score / total * 100);

    document.getElementById('result-score').textContent = score + '/' + total;
    document.getElementById('result-pct').textContent = pct + '%';

    // Animate circle
    const circle = document.getElementById('score-circle');
    circle.style.setProperty('--pct', pct + '%');

    let emoji, msg, sub;
    if (pct >= 90) { emoji = '🏆'; msg = 'Xuất sắc!'; sub = 'Kết quả tuyệt vời, tiếp tục phát huy nhé!'; }
    else if (pct >= 70) { emoji = '🎉'; msg = 'Giỏi lắm!'; sub = 'Bạn đã nắm khá vững kiến thức này!'; }
    else if (pct >= 50) { emoji = '👍'; msg = 'Khá tốt!'; sub = 'Ôn thêm một chút là hoàn hảo rồi!'; }
    else { emoji = '💪'; msg = 'Cố lên!'; sub = 'Đừng nản, hãy làm lại để cải thiện điểm số!'; }

    document.getElementById('result-emoji').textContent = emoji;
    document.getElementById('result-msg').textContent = msg;
    document.getElementById('result-sub').textContent = sub;

    // Update progress
    document.getElementById('q-progress').style.width = '100%';
    document.getElementById('q-counter').textContent = quizState.questions.length + ' / ' + quizState.questions.length;
}

function retryQuiz() {
    startQuiz(quizState.topic);
}

// ============================
// UI HELPERS
// ============================
function selectSubject(el) {
    document.querySelectorAll('.subject-card').forEach(c => c.classList.remove('active'));
    el.classList.add('active');
}

function selectLesson(el, title) {
    document.querySelectorAll('.lesson-item').forEach(i => i.classList.remove('highlight'));
    el.classList.add('highlight');
    document.getElementById('topic-title').textContent = title;
}

function clearErrors(ids) {
    ids.forEach(id => {
        const el = document.getElementById(id);
        if (el) el.textContent = '';
    });
}

function showToast(msg, type = 'success') {
    const t = document.getElementById('toast');
    t.textContent = msg;
    t.className = 'toast-msg ' + type + ' show';
    setTimeout(() => t.className = 'toast-msg', 3000);
}

function shuffle(arr) {
    for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
    }
    return arr;
}
const LESSON_EXERCISES = {
    'Đơn thức nhiều biến': `
        <div class="col-sm-6">
            <div class="grid-card" onclick="startQuiz('Đơn thức nhiều biến')">
                <div class="card-icon">📐</div>
                <div class="card-title">Đơn thức nhiều biến</div>
                <div class="card-sub">5 câu hỏi · ~5 phút</div>
            </div>
        </div>

        <div class="col-sm-6">
            <div class="grid-card" onclick="startQuiz('Đa thức nhiều biến')">
                <div class="card-icon">📊</div>
                <div class="card-title">Đa thức nhiều biến</div>
                <div class="card-sub">5 câu hỏi · ~5 phút</div>
            </div>
        </div>
    `,

    'Phép cộng trừ đơn thức': `
        <div class="col-sm-6">
            <div class="grid-card" onclick="startQuiz('Phép cộng trừ đa thức')">
                <div class="card-icon">➕</div>
                <div class="card-title">Phép cộng trừ đa thức</div>
                <div class="card-sub">4 câu hỏi · ~4 phút</div>
            </div>
        </div>
    `,

    'Phân tích nhân tử': `
        <div class="col-sm-6">
            <div class="grid-card">
                <div class="card-icon">🧩</div>
                <div class="card-title">Phân tích đa thức thành nhân tử</div>
                <div class="card-sub">5 câu hỏi · ~5 phút</div>
            </div>
        </div>
    `,

    'Hằng đẳng thức': `
        <div class="col-sm-6">
            <div class="grid-card" onclick="startQuiz('Hằng đẳng thức')">
                <div class="card-icon">⚡</div>
                <div class="card-title">Hằng đẳng thức đáng nhớ</div>
                <div class="card-sub">5 câu hỏi · ~6 phút</div>
            </div>
        </div>
    `
};

// sửa hàm selectLesson để đổi bài tập
const oldSelectLesson = selectLesson;

selectLesson = function(el, title){
    oldSelectLesson(el, title);

    const container = document.querySelector(".row.g-3");

    if(LESSON_EXERCISES[title]){
        container.innerHTML = LESSON_EXERCISES[title];
    }
}
const formulas = ["x²", "y=ax+b", "π", "√", "∑", "∫", "sin", "cos", "tan", "cot", "1+1=2", "3/4 - 7/8"];
const container = document.querySelector(".math-bg");

for (let i = 0; i < 100; i++) {
    let span = document.createElement("span");
    span.innerText = formulas[Math.floor(Math.random()*formulas.length)];

    span.style.left = Math.random()*100 + "vw";
    span.style.fontSize = (20 + Math.random()*30) + "px";
    span.style.animationDuration = (4 + Math.random()*4) + "s";
    span.style.animationDelay = Math.random() * 4 + "s";

    container.appendChild(span);
}
setInterval(() => {
    let span = document.createElement("span");
    span.innerText = formulas[Math.floor(Math.random()*formulas.length)];

    span.style.left = Math.random()*100 + "vw";
    span.style.fontSize = (20 + Math.random()*30) + "px";
    span.style.animationDuration = (6 + Math.random()*6) + "s";
    span.style.animationDelay = "0s";

    container.appendChild(span);

    // Xóa sau khi bay xong để tránh lag
    setTimeout(() => {
        span.remove();
    }, 10000);

}, 300);

</script>
</body>
</html>
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MinhEdu - Học tập chủ động</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #d4e815;
            --primary-dark: #b8cc00;
            --primary-light: #f1f8a4;
            --dark: #1a1a2e;
            --mid: #333;
            --bg: #f5f7f0;
            --white: #ffffff;
            --danger: #e53935;
            --success: #43a047;
            --info: #039be5;
            --radius: 16px;
            --shadow: 0 8px 32px rgba(0,0,0,0.10);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }

       body {
            font-family: 'Nunito', sans-serif;
            background: #f5f7f0;
            color: #333;
        }
        .section {
        padding: 30px;
        }
        h2 { margin-bottom: 20px; }

        /* COMMON CARD */
        .card {
        border-radius: 16px;
        padding: 20px;
        margin: 10px;
        display: inline-block;
        width: 200px;
        }

        /* ================= GAMING STYLE ================= */
        .gaming { background: linear-gradient(135deg,#1a1a1a,#000); }
        .gaming .card {
        background: #222;
        border: 2px solid gold;
        box-shadow: 0 0 15px gold;
        text-align: center;
        }

        /* ================= STUDY STYLE ================= */
        .study { background: #f5f5f5; color: black; }
        .study .card {
        background: white;
        border: 1px solid #ddd;
        }
        .progress {
        height: 10px;
        background: #ddd;
        border-radius: 10px;
        overflow: hidden;
        }
        .progress div {
        height: 100%;
        background: gold;
        width: 70%;
        }

        /* ================= MINIMAL STYLE ================= */
        .minimal { background: #fff; color: black; }
        .minimal .card {
        border: 1px solid #eee;
        transition: 0.3s;
        }
        .minimal .card:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }


        /* ===== PAGE SYSTEM ===== */
        .page { display: none; }
        .page.active { display: block; }

        /* ===== AUTH PAGES ===== */
        .auth-page {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 20px;
        }

        .auth-box {
            background: white;
            border-radius: 24px;
            padding: 44px 40px;
            width: 100%;
            max-width: 420px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.25);
            animation: slideIn 0.4s ease-out;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(-24px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .auth-logo {
            text-align: center;
            margin-bottom: 28px;
        }

        .auth-logo h1 {
            font-size: 36px;
            font-weight: 900;
            color: var(--primary);
            letter-spacing: -1px;
            text-shadow: 2px 3px 0 #c4d800;
        }

        .auth-logo p {
            color: #888;
            font-size: 15px;
            margin-top: 4px;
        }

        .form-field {
            margin-bottom: 18px;
        }

        .form-field label {
            display: block;
            margin-bottom: 7px;
            font-weight: 700;
            font-size: 14px;
            color: #444;
        }

        .form-field input {
            width: 100%;
            padding: 13px 16px;
            border: 2px solid #e5e5e5;
            border-radius: 12px;
            font-size: 15px;
            font-family: inherit;
            transition: 0.2s;
            background: #fafafa;
            color: #222;
        }

        .form-field input:focus {
            outline: none;
            border-color: var(--primary);
            background: white;
            box-shadow: 0 0 0 4px rgba(212,232,21,0.15);
        }

        .err-msg {
            display: block;
            color: var(--danger);
            font-size: 12px;
            font-weight: 600;
            margin-top: 5px;
            min-height: 16px;
        }

        .btn-primary-auth {
            width: 100%;
            padding: 14px;
            background: var(--primary);
            color: #222;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 800;
            cursor: pointer;
            transition: 0.2s;
            margin-top: 6px;
            letter-spacing: 0.3px;
        }

        .btn-primary-auth:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(180,210,0,0.35);
        }

        .auth-footer {
            text-align: center;
            margin-top: 22px;
            padding-top: 20px;
            border-top: 1px solid #eee;
        }

        .auth-footer p { color: #777; font-size: 14px; margin-bottom: 8px; }

        .auth-footer a {
            color: #764ba2;
            font-weight: 700;
            text-decoration: none;
            cursor: pointer;
        }

        .auth-footer a:hover { text-decoration: underline; }

        /* ===== MAIN APP ===== */
        #page-main { display: none; flex-direction: column; min-height: 100vh; }
        #page-main.active { display: flex; }

        .header-top {
            background: white;
            padding: 12px 0;
            border-bottom: 1px solid #eee;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        }

        .search-box {
            border: 1.5px solid #ddd;
            border-radius: 50px;
            padding: 7px 16px;
            display: flex;
            align-items: center;
            max-width: 280px;
            background: #fafafa;
        }

        .search-box input {
            border: none;
            outline: none;
            background: transparent;
            width: 100%;
            margin-left: 8px;
            font-size: 14px;
            font-family: inherit;
        }

        .user-chip {
            display: flex;
            align-items: center;
            gap: 8px;
            background: var(--primary-light);
            border: 1.5px solid var(--primary);
            border-radius: 50px;
            padding: 6px 16px 6px 10px;
            font-weight: 700;
            font-size: 14px;
            color: #333;
        }

        .user-chip .avatar {
            width: 28px; height: 28px;
            background: var(--primary);
            border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            font-weight: 900; font-size: 13px;
        }

        .btn-logout {
            background: #f0f0f0;
            border: none;
            border-radius: 50px;
            padding: 7px 18px;
            font-size: 13px;
            font-weight: 700;
            cursor: pointer;
            color: #555;
            transition: 0.2s;
        }

        .btn-logout:hover { background: #e0e0e0; color: #333; }

        .navbar-custom {
            background: var(--dark);
            padding: 0;
            overflow-x: auto;
        }

        .navbar-custom::-webkit-scrollbar { height: 3px; }
        .navbar-custom::-webkit-scrollbar-thumb { background: var(--primary); }

        .navbar-nav-custom {
            display: flex;
            white-space: nowrap;
            padding: 0 16px;
        }

        .navbar-nav-custom a {
            color: rgba(255,255,255,0.75) !important;
            font-weight: 700;
            padding: 13px 18px !important;
            text-transform: uppercase;
            font-size: 12px;
            letter-spacing: 0.5px;
            text-decoration: none;
            display: inline-block;
            transition: 0.2s;
            border-bottom: 3px solid transparent;
        }

        .navbar-nav-custom a:hover,
        .navbar-nav-custom a.active {
            color: var(--primary) !important;
            border-bottom-color: var(--primary);
        }

        /* Subject cards */
        .subject-card {
            background: white;
            border-radius: 14px;
            padding: 14px 20px;
            text-align: center;
            border: 2px solid #eee;
            cursor: pointer;
            transition: 0.2s;
            min-width: 110px;
        }

        .subject-card:hover { border-color: var(--primary); box-shadow: 0 4px 12px rgba(0,0,0,0.08); }
        .subject-card.active { border-color: var(--dark); background: var(--primary-light); }
        .subject-icon { width: 38px; margin-bottom: 8px; }

        /* Sidebar */
        .sidebar-title {
            background: var(--dark);
            color: var(--primary);
            padding: 14px 18px;
            border-radius: 14px 14px 0 0;
            font-weight: 800;
            font-size: 14px;
            letter-spacing: 0.3px;
        }

        .lesson-container {
            background: white;
            border-radius: 0 0 14px 14px;
            padding: 14px;
            min-height: 380px;
            box-shadow: var(--shadow);
        }

        .lesson-item {
            background: #f9f9f9;
            border: 1.5px solid #eee;
            border-radius: 12px;
            padding: 12px 14px;
            margin-bottom: 10px;
            cursor: pointer;
            transition: 0.2s;
        }

        .lesson-item:hover { border-color: var(--primary); }
        .lesson-item.highlight { background: var(--primary-light); border-color: var(--primary); }

        /* Topic & cards */
        .topic-header {
            background: white;
            border-radius: 14px;
            padding: 20px;
            border: 1.5px solid #eee;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
        }

        .grid-card {
            background: linear-gradient(135deg, #ffe082 0%, #ffca28 100%);
            border-radius: 16px;
            padding: 28px 20px;
            cursor: pointer;
            transition: 0.25s;
            box-shadow: 0 4px 16px rgba(255,200,0,0.2);
            border: 2px solid transparent;
            height: 100%;
        }

        .grid-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 12px 32px rgba(255,180,0,0.3);
            border-color: var(--primary-dark);
        }

        .grid-card .card-title {
            font-weight: 800;
            font-size: 16px;
            color: #333;
            margin-bottom: 6px;
        }

        .grid-card .card-sub {
            font-size: 13px;
            color: #666;
        }

        .grid-card .card-icon {
            font-size: 28px;
            margin-bottom: 10px;
        }

        /* ===== QUIZ PAGE ===== */
        .quiz-page {
            min-height: 100vh;
            background: linear-gradient(160deg, #1a1a2e 0%, #16213e 60%, #0f3460 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 24px;
        }

        .quiz-box {
            width: 100%;
            max-width: 680px;
            background: white;
            border-radius: 24px;
            padding: 40px;
            box-shadow: 0 24px 80px rgba(0,0,0,0.4);
            animation: slideIn 0.4s ease-out;
        }

        .quiz-header-bar {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 24px;
        }

        .quiz-logo {
            font-size: 22px;
            font-weight: 900;
            color: var(--primary);
            letter-spacing: -0.5px;
        }

        .q-counter {
            background: var(--primary-light);
            border: 1.5px solid var(--primary);
            border-radius: 50px;
            padding: 5px 16px;
            font-size: 13px;
            font-weight: 800;
            color: #444;
        }

        .progress-track {
            height: 8px;
            background: #f0f0f0;
            border-radius: 99px;
            margin-bottom: 28px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary-dark), var(--primary));
            border-radius: 99px;
            transition: width 0.4s ease;
        }

        .question-text {
            font-size: 20px;
            font-weight: 800;
            color: #1a1a2e;
            margin-bottom: 24px;
            line-height: 1.45;
        }

        .question-num {
            font-size: 12px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: #aaa;
            margin-bottom: 8px;
        }

        .option-btn {
            display: block;
            width: 100%;
            text-align: left;
            padding: 15px 20px;
            border: 2px solid #e8e8e8;
            border-radius: 12px;
            background: #fafafa;
            font-size: 15px;
            font-weight: 600;
            font-family: inherit;
            color: #333;
            cursor: pointer;
            margin-bottom: 12px;
            transition: 0.18s;
            position: relative;
        }

        .option-btn:hover:not(:disabled) {
            border-color: var(--primary);
            background: var(--primary-light);
            transform: translateX(4px);
        }

        .option-btn.selected {
            border-color: var(--primary);
            background: var(--primary-light);
        }

        .option-btn.correct {
            border-color: var(--success) !important;
            background: #e8f5e9 !important;
            color: #1b5e20 !important;
        }

        .option-btn.correct::after {
            content: ' ✓';
            font-weight: 900;
            color: var(--success);
        }

        .option-btn.incorrect {
            border-color: var(--danger) !important;
            background: #ffebee !important;
            color: #b71c1c !important;
        }

        .option-btn.incorrect::after {
            content: ' ✗';
            font-weight: 900;
            color: var(--danger);
        }

        .option-btn:disabled { cursor: default; }

        .feedback-box {
            margin-top: 16px;
            padding: 14px 18px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 15px;
            display: none;
        }

        .feedback-box.show { display: block; animation: feedbackIn 0.3s ease; }

        @keyframes feedbackIn {
            from { opacity: 0; transform: scale(0.96); }
            to { opacity: 1; transform: scale(1); }
        }

        .feedback-box.correct-fb {
            background: #e8f5e9;
            color: #1b5e20;
            border: 1.5px solid #81c784;
        }

        .feedback-box.incorrect-fb {
            background: #ffebee;
            color: #b71c1c;
            border: 1.5px solid #e57373;
        }

        .btn-next-q {
            width: 100%;
            padding: 14px;
            background: var(--dark);
            color: var(--primary);
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 20px;
            transition: 0.2s;
            letter-spacing: 0.3px;
        }

        .btn-next-q:hover { background: #2d2d50; transform: translateY(-2px); }
        .btn-next-q:disabled { background: #ccc; color: #888; cursor: not-allowed; transform: none; }

        /* Result */
        .result-screen { text-align: center; padding: 20px 0; }
        .score-circle {
            width: 140px; height: 140px;
            border-radius: 50%;
            background: conic-gradient(var(--primary) var(--pct, 0%), #f0f0f0 0%);
            display: flex; align-items: center; justify-content: center;
            margin: 0 auto 20px;
            position: relative;
            box-shadow: 0 8px 32px rgba(180,210,0,0.25);
        }

        .score-circle-inner {
            width: 112px; height: 112px;
            background: white;
            border-radius: 50%;
            display: flex; flex-direction: column;
            align-items: center; justify-content: center;
        }

        .score-num {
            font-size: 32px;
            font-weight: 900;
            color: var(--dark);
            line-height: 1;
        }

        .score-total { font-size: 13px; color: #aaa; font-weight: 700; }

        .result-emoji { font-size: 48px; margin-bottom: 10px; }
        .result-msg { font-size: 20px; font-weight: 800; color: #333; }
        .result-sub { font-size: 15px; color: #888; margin-top: 8px; }

        .btn-retry {
            display: inline-block;
            padding: 12px 32px;
            background: var(--primary);
            color: #333;
            border: none;
            border-radius: 50px;
            font-size: 15px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 24px;
            margin-right: 10px;
            transition: 0.2s;
        }

        .btn-retry:hover { background: var(--primary-dark); transform: translateY(-2px); }

        .btn-home {
            display: inline-block;
            padding: 12px 32px;
            background: var(--dark);
            color: var(--primary);
            border: none;
            border-radius: 50px;
            font-size: 15px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 24px;
            transition: 0.2s;
        }

        .btn-home:hover { background: #2d2d50; transform: translateY(-2px); }

        /* Toast */
        .toast-msg {
            position: fixed;
            top: 20px; right: 20px;
            background: #222;
            color: #fff;
            padding: 14px 22px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 14px;
            z-index: 9999;
            transform: translateX(200px);
            opacity: 0;
            transition: 0.3s;
            max-width: 300px;
        }

        .toast-msg.show { transform: translateX(0); opacity: 1; }
        .toast-msg.success { border-left: 4px solid var(--primary); }
        .toast-msg.error { border-left: 4px solid var(--danger); }

        @media (max-width: 600px) {
            .auth-box, .quiz-box { padding: 28px 20px; }
            .question-text { font-size: 17px; }
        }
        .shelf-row {
            display: flex;
            gap: 20px;
            align-items: flex-end; /* QUAN TRỌNG: đứng trên kệ */
            position: relative;
            padding-bottom: 20px;
        }

        /* THANH GỖ */
        .shelf-row::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 10px;
            background: linear-gradient(90deg, #8b5a2b, #c49a6c);
            border-radius: 6px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
        }

        /* CUỐN SÁCH */
        .book {
            width: 90px;
            height: 130px;
            background: linear-gradient(180deg, #ffe082, #ffca28);
            border-radius: 6px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            font-weight: 700;
            font-size: 12px;
            text-align: center;
            color: #333;
            cursor: pointer;
            transition: 0.2s;
            position: relative;
        }

        /* GÁY SÁCH */
        .book::before {
            content: "";
            position: absolute;
            left: 0;
            top: 0;
            width: 6px;
            height: 100%;
            background: #e0b000;
            border-radius: 6px 0 0 6px;
        }

        .book i {
            font-size: 20px;
            margin-bottom: 6px;
        }

        /* HOVER */
        .book:hover {
            transform: translateY(-10px);
        }

        /* CHƯA MỞ */
        .book.locked {
            background: #ddd;
            color: #999;
        }

        .book.locked::before {
            background: #bbb;
        }
        /* ===== TAB MENU ===== */
        .achievement-tabs {
            display: flex;
            gap: 10px;
            margin: 20px;
        }

        .tab {
            padding: 10px 20px;
            background: #eee;
            border-radius: 10px;
            font-weight: 700;
            cursor: pointer;
            transition: 0.2s;
        }

        .tab:hover {
            background: #ddd;
        }

        .tab.active {
            background: linear-gradient(135deg, #ffe082, #ffca28);
            color: #333;
        }

        /* CONTENT BOX */
        .achievement-content {
            background: white;
            margin: 0 20px;
            padding: 20px;
            border-radius: 16px;
            box-shadow: var(--shadow);
        }
        .achievement-list {
            margin-top: 10px;
        }

        /* CARD */
        .achievement-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: #f5f5f5;
            border-radius: 12px;
            padding: 14px 18px;
            border: 1px solid #ddd;
            transition: 0.2s;
        }

        /* HOVER */
        .achievement-item:hover {
            background: #fff8dc;
            border-color: #f4c542;
        }

        /* ICON */
        .achievement-item i {
            font-size: 22px;
            color: #f4c542;
            margin-right: 12px;
        }

        /* TEXT */
        .achievement-item .content {
            flex: 1;
        }

        .achievement-item b {
            font-size: 15px;
        }

        .achievement-item p {
            margin: 0;
            font-size: 12px;
            color: #777;
        }

        /* BUTTON */
        .achievement-item button {
            background: white;
            border: 1px solid #ccc;
            border-radius: 20px;
            padding: 5px 14px;
            cursor: pointer;
        }

        /* LOCKED */
        .achievement-item.locked {
            opacity: 0.6;
        }

        .achievement-item.locked i {
            color: #aaa;
        }
    </style>
</head>
<body>

<!-- TOAST -->
<div class="toast-msg" id="toast"></div>

<!-- ===== PAGE: ĐĂNG NHẬP ===== -->
<div id="page-login" class="page active">
    <div class="auth-page">
        <div class="auth-box">
            <div class="auth-logo">
                <h1>MinhEdu</h1>
                <p>Đăng nhập vào tài khoản của bạn</p>
            </div>
            <div class="form-field">
                <label>Email</label>
                <input type="email" id="login-email" placeholder="Nhập email của bạn">
                <span class="err-msg" id="login-email-err"></span>
            </div>
            <div class="form-field">
                <label>Mật khẩu</label>
                <input type="password" id="login-password" placeholder="Nhập mật khẩu" onkeydown="if(event.key==='Enter') doLogin()">
                <span class="err-msg" id="login-pass-err"></span>
            </div>
            <button class="btn-primary-auth" onclick="doLogin()">Đăng nhập</button>
            <div class="auth-footer">
                <p>Chưa có tài khoản? <a onclick="showPage('page-register')">Đăng ký ngay</a></p>
                <a onclick="showPage('page-main')">← Vào xem trang chính</a>
            </div>
        </div>
    </div>
</div>

<!-- ===== PAGE: ĐĂNG KÝ ===== -->
<div id="page-register" class="page">
    <div class="auth-page">
        <div class="auth-box">
            <div class="auth-logo">
                <h1>MinhEdu</h1>
                <p>Tạo tài khoản mới</p>
            </div>
            <div class="form-field">
                <label>Họ và tên</label>
                <input type="text" id="reg-name" placeholder="Nguyễn Văn A">
                <span class="err-msg" id="reg-name-err"></span>
            </div>
            <div class="form-field">
                <label>Email</label>
                <input type="email" id="reg-email" placeholder="email@example.com">
                <span class="err-msg" id="reg-email-err"></span>
            </div>
            <div class="form-field">
                <label>Mật khẩu</label>
                <input type="password" id="reg-pass" placeholder="Tối thiểu 6 ký tự">
                <span class="err-msg" id="reg-pass-err"></span>
            </div>
            <div class="form-field">
                <label>Xác nhận mật khẩu</label>
                <input type="password" id="reg-confirm" placeholder="Nhập lại mật khẩu" onkeydown="if(event.key==='Enter') doRegister()">
                <span class="err-msg" id="reg-confirm-err"></span>
            </div>
            <button class="btn-primary-auth" onclick="doRegister()">Đăng ký</button>
            <div class="auth-footer">
                <p>Đã có tài khoản? <a onclick="showPage('page-login')">Đăng nhập</a></p>
                <a onclick="showPage('page-main')">← Vào xem trang chính</a>
            </div>
        </div>
    </div>
</div>
<div id="page-main" class="page">
    <header class="header-top">
        <div class="container d-flex justify-content-between align-items-center">
            <div class="d-flex align-items-center gap-3">
                <div style="font-weight:900;font-size:22px;color:var(--dark);letter-spacing:-0.5px;">MinhEdu</div>
                <div class="search-box">
                    <i class="fas fa-search" style="color:#bbb;font-size:13px;"></i>
                    <input type="text" placeholder="Tìm kiếm bài học...">
                </div>
            </div>
            <div class="d-flex align-items-center gap-2" id="header-auth-area">
                <button class="btn btn-dark rounded-pill px-4 fw-bold" style="font-size:14px;" onclick="showPage('page-login')">Đăng nhập</button>
                <button class="btn rounded-pill px-4 fw-bold" style="background:var(--primary);font-size:14px;" onclick="showPage('page-register')">Đăng ký</button>
            </div>
        </div>
    </header>

    <nav class="navbar-custom">
        <div class="container">
            <div class="navbar-nav-custom">
                <a href="MinhEdu_Vaohoc.html">Vào học</a>
                <a href="MinhEdu_Nhatkyhoctap.html">Nhật ký học tập</a>
                <a href="MinhEdu_Doiqua.html">Đổi quà</a>
                <a href="MinhEdu_ThanhTich.html" class="active">Thành tích</a>
                <a href="MinhEdu_MuaKhoaHoc.html">Mua khóa học</a>

            </div>
        </div>
    </nav>

    <div class="container">
        <div class="achievement-tabs">
            <div class="tab active">🏆 Giấy chứng nhận</div>
            <div class="tab">🔥 Giấy khen</div>
            <div class="tab">⚡ Huy Hiệu</div>
        </div>

        <div class="achievement-content">
            <div class="achievement-list">

                    <div class="achievement-item">
                        <i class="fas fa-trophy"></i>
                        <div class="content">
                            <b>100 điểm đầu tiên</b>
                            <p>Hoàn thành bài đầu tiên</p>
                        </div>
                        <button>Xem</button>
                    </div>

                    <div class="achievement-item">
                        <i class="fas fa-fire"></i>
                        <div class="content">
                            <b>7 ngày liên tiếp</b>
                            <p>Học đều đặn</p>
                        </div>
                        <button>Xem</button>
                    </div>

                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                    <div class="achievement-item locked">
                        <i class="fas fa-lock"></i>
                        <div class="content">
                            <b>Chưa mở</b>
                            <p>???</p>
                        </div>
                        <button disabled>Khoá</button>
                    </div>
                </div>

            </div>
        </div>
    </div>
</div>

<script>

// ============================
// STATE
// ============================
let currentUser = null;
let quizState = {
    topic: '',
    questions: [],
    current: 0,
    score: 0,
    answered: false
};

// ============================
// INIT
// ============================
window.addEventListener('load', () => {
    const saved = localStorage.getItem('minhedu_user');
    if (saved) {
        currentUser = JSON.parse(saved);
        updateHeaderForUser();
        showPage('page-main');
    } else {
        showPage('page-login');
    }
});

// ============================
// PAGE NAV
// ============================
function showPage(id) {
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    window.scrollTo(0, 0);
}

// ============================
// AUTH
// ============================
function getUsers() {
    return JSON.parse(localStorage.getItem('minhedu_users') || '[]');
}

function saveUsers(users) {
    localStorage.setItem('minhedu_users', JSON.stringify(users));
}

function doLogin() {
    clearErrors(['login-email-err', 'login-pass-err']);
    const email = document.getElementById('login-email').value.trim();
    const pass = document.getElementById('login-password').value;

    let ok = true;
    if (!email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) {
        document.getElementById('login-email-err').textContent = 'Email không hợp lệ';
        ok = false;
    }
    if (pass.length < 6) {
        document.getElementById('login-pass-err').textContent = 'Mật khẩu phải ít nhất 6 ký tự';
        ok = false;
    }
    if (!ok) return;

    const users = getUsers();
    const user = users.find(u => u.email === email && u.password === pass);

    if (!user) {
        document.getElementById('login-pass-err').textContent = 'Email hoặc mật khẩu không chính xác';
        return;
    }

    currentUser = { id: user.id, name: user.name, email: user.email };
    localStorage.setItem('minhedu_user', JSON.stringify(currentUser));
    showToast('Chào mừng trở lại, ' + user.name + '! 👋', 'success');
    updateHeaderForUser();
    document.getElementById('login-email').value = '';
    document.getElementById('login-password').value = '';
    showPage('page-main');
}

function doRegister() {
    clearErrors(['reg-name-err', 'reg-email-err', 'reg-pass-err', 'reg-confirm-err']);
    const name = document.getElementById('reg-name').value.trim();
    const email = document.getElementById('reg-email').value.trim();
    const pass = document.getElementById('reg-pass').value;
    const confirm = document.getElementById('reg-confirm').value;

    let ok = true;
    if (name.length < 3) { document.getElementById('reg-name-err').textContent = 'Tên phải ít nhất 3 ký tự'; ok = false; }
    if (!email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) { document.getElementById('reg-email-err').textContent = 'Email không hợp lệ'; ok = false; }
    if (pass.length < 6) { document.getElementById('reg-pass-err').textContent = 'Mật khẩu phải ít nhất 6 ký tự'; ok = false; }
    if (pass !== confirm) { document.getElementById('reg-confirm-err').textContent = 'Mật khẩu không khớp'; ok = false; }
    if (!ok) return;

    const users = getUsers();
    if (users.find(u => u.email === email)) {
        document.getElementById('reg-email-err').textContent = 'Email đã được đăng ký!';
        return;
    }

    const newUser = { id: Date.now(), name, email, password: pass };
    users.push(newUser);
    saveUsers(users);

    currentUser = { id: newUser.id, name: newUser.name, email: newUser.email };
    localStorage.setItem('minhedu_user', JSON.stringify(currentUser));
    showToast('Đăng ký thành công! Chào mừng, ' + name + '! 🎉', 'success');
    updateHeaderForUser();
    document.getElementById('reg-name').value = '';
    document.getElementById('reg-email').value = '';
    document.getElementById('reg-pass').value = '';
    document.getElementById('reg-confirm').value = '';
    showPage('page-main');
}

function doLogout() {
    currentUser = null;
    localStorage.removeItem('minhedu_user');
    showToast('Đã đăng xuất', 'success');
    updateHeaderForUser();
}

function updateHeaderForUser() {
    const area = document.getElementById('header-auth-area');
    if (currentUser) {
        const initial = currentUser.name.charAt(0).toUpperCase();
        area.innerHTML = `
            <div class="user-chip">
                <div class="avatar">${initial}</div>
                <span>${currentUser.name}</span>
            </div>
            <button class="btn-logout" onclick="doLogout()">Đăng xuất</button>
        `;
    } else {
        area.innerHTML = `
            <button class="btn btn-dark rounded-pill px-4 fw-bold" style="font-size:14px;" onclick="showPage('page-login')">Đăng nhập</button>
            <button class="btn rounded-pill px-4 fw-bold" style="background:var(--primary);font-size:14px;" onclick="showPage('page-register')">Đăng ký</button>
        `;
    }
}

</script>
</body>
</html>
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MinhEdu - Học tập chủ động</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #d4e815;
            --primary-dark: #b8cc00;
            --primary-light: #f1f8a4;
            --dark: #1a1a2e;
            --mid: #333;
            --bg: #f5f7f0;
            --white: #ffffff;
            --danger: #e53935;
            --success: #43a047;
            --info: #039be5;
            --radius: 16px;
            --shadow: 0 8px 32px rgba(0,0,0,0.10);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }

        body {
            font-family: 'Nunito', sans-serif;
            background: var(--bg);
            min-height: 100vh;
        }

        /* ===== PAGE SYSTEM ===== */
        .page { display: none; }
        .page.active { display: block; }

        /* ===== AUTH PAGES ===== */
        .auth-page {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 20px;
        }

        .auth-box {
            background: white;
            border-radius: 24px;
            padding: 44px 40px;
            width: 100%;
            max-width: 420px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.25);
            animation: slideIn 0.4s ease-out;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(-24px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .auth-logo {
            text-align: center;
            margin-bottom: 28px;
        }

        .auth-logo h1 {
            font-size: 36px;
            font-weight: 900;
            color: var(--primary);
            letter-spacing: -1px;
            text-shadow: 2px 3px 0 #c4d800;
        }

        .auth-logo p {
            color: #888;
            font-size: 15px;
            margin-top: 4px;
        }

        .form-field {
            margin-bottom: 18px;
        }

        .form-field label {
            display: block;
            margin-bottom: 7px;
            font-weight: 700;
            font-size: 14px;
            color: #444;
        }

        .form-field input {
            width: 100%;
            padding: 13px 16px;
            border: 2px solid #e5e5e5;
            border-radius: 12px;
            font-size: 15px;
            font-family: inherit;
            transition: 0.2s;
            background: #fafafa;
            color: #222;
        }

        .form-field input:focus {
            outline: none;
            border-color: var(--primary);
            background: white;
            box-shadow: 0 0 0 4px rgba(212,232,21,0.15);
        }

        .err-msg {
            display: block;
            color: var(--danger);
            font-size: 12px;
            font-weight: 600;
            margin-top: 5px;
            min-height: 16px;
        }

        .btn-primary-auth {
            width: 100%;
            padding: 14px;
            background: var(--primary);
            color: #222;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 800;
            cursor: pointer;
            transition: 0.2s;
            margin-top: 6px;
            letter-spacing: 0.3px;
        }

        .btn-primary-auth:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(180,210,0,0.35);
        }

        .auth-footer {
            text-align: center;
            margin-top: 22px;
            padding-top: 20px;
            border-top: 1px solid #eee;
        }

        .auth-footer p { color: #777; font-size: 14px; margin-bottom: 8px; }

        .auth-footer a {
            color: #764ba2;
            font-weight: 700;
            text-decoration: none;
            cursor: pointer;
        }

        .auth-footer a:hover { text-decoration: underline; }

        /* ===== MAIN APP ===== */
        #page-main { display: none; flex-direction: column; min-height: 100vh; }
        #page-main.active { display: flex; }

        .header-top {
            background: white;
            padding: 12px 0;
            border-bottom: 1px solid #eee;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        }

        .search-box {
            border: 1.5px solid #ddd;
            border-radius: 50px;
            padding: 7px 16px;
            display: flex;
            align-items: center;
            max-width: 280px;
            background: #fafafa;
        }

        .search-box input {
            border: none;
            outline: none;
            background: transparent;
            width: 100%;
            margin-left: 8px;
            font-size: 14px;
            font-family: inherit;
        }

        .user-chip {
            display: flex;
            align-items: center;
            gap: 8px;
            background: var(--primary-light);
            border: 1.5px solid var(--primary);
            border-radius: 50px;
            padding: 6px 16px 6px 10px;
            font-weight: 700;
            font-size: 14px;
            color: #333;
        }

        .user-chip .avatar {
            width: 28px; height: 28px;
            background: var(--primary);
            border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            font-weight: 900; font-size: 13px;
        }

        .btn-logout {
            background: #f0f0f0;
            border: none;
            border-radius: 50px;
            padding: 7px 18px;
            font-size: 13px;
            font-weight: 700;
            cursor: pointer;
            color: #555;
            transition: 0.2s;
        }

        .btn-logout:hover { background: #e0e0e0; color: #333; }

        .navbar-custom {
            background: var(--dark);
            padding: 0;
            overflow-x: auto;
        }

        .navbar-custom::-webkit-scrollbar { height: 3px; }
        .navbar-custom::-webkit-scrollbar-thumb { background: var(--primary); }

        .navbar-nav-custom {
            display: flex;
            white-space: nowrap;
            padding: 0 16px;
        }

        .navbar-nav-custom a {
            color: rgba(255,255,255,0.75) !important;
            font-weight: 700;
            padding: 13px 18px !important;
            text-transform: uppercase;
            font-size: 12px;
            letter-spacing: 0.5px;
            text-decoration: none;
            display: inline-block;
            transition: 0.2s;
            border-bottom: 3px solid transparent;
        }

        .navbar-nav-custom a:hover,
        .navbar-nav-custom a.active {
            color: var(--primary) !important;
            border-bottom-color: var(--primary);
        }

        /* Subject cards */
        .subject-card {
            background: white;
            border-radius: 14px;
            padding: 14px 20px;
            text-align: center;
            border: 2px solid #eee;
            cursor: pointer;
            transition: 0.2s;
            min-width: 110px;
        }

        .subject-card:hover { border-color: var(--primary); box-shadow: 0 4px 12px rgba(0,0,0,0.08); }
        .subject-card.active { border-color: var(--dark); background: var(--primary-light); }
        .subject-icon { width: 38px; margin-bottom: 8px; }

        /* Sidebar */
        .sidebar-title {
            background: var(--dark);
            color: var(--primary);
            padding: 14px 18px;
            border-radius: 14px 14px 0 0;
            font-weight: 800;
            font-size: 14px;
            letter-spacing: 0.3px;
        }

        .lesson-container {
            background: white;
            border-radius: 0 0 14px 14px;
            padding: 14px;
            min-height: 380px;
            box-shadow: var(--shadow);
        }

        .lesson-item {
            background: #f9f9f9;
            border: 1.5px solid #eee;
            border-radius: 12px;
            padding: 12px 14px;
            margin-bottom: 10px;
            cursor: pointer;
            transition: 0.2s;
        }

        .lesson-item:hover { border-color: var(--primary); }
        .lesson-item.highlight { background: var(--primary-light); border-color: var(--primary); }

        /* Topic & cards */
        .topic-header {
            background: white;
            border-radius: 14px;
            padding: 20px;
            border: 1.5px solid #eee;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
        }

        .grid-card {
            background: linear-gradient(135deg, #ffe082 0%, #ffca28 100%);
            border-radius: 16px;
            padding: 28px 20px;
            cursor: pointer;
            transition: 0.25s;
            box-shadow: 0 4px 16px rgba(255,200,0,0.2);
            border: 2px solid transparent;
            height: 100%;
        }

        .grid-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 12px 32px rgba(255,180,0,0.3);
            border-color: var(--primary-dark);
        }

        .grid-card .card-title {
            font-weight: 800;
            font-size: 16px;
            color: #333;
            margin-bottom: 6px;
        }

        .grid-card .card-sub {
            font-size: 13px;
            color: #666;
        }

        .grid-card .card-icon {
            font-size: 28px;
            margin-bottom: 10px;
        }

        /* ===== QUIZ PAGE ===== */
        .quiz-page {
            min-height: 100vh;
            background: linear-gradient(160deg, #1a1a2e 0%, #16213e 60%, #0f3460 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 24px;
        }

        .quiz-box {
            width: 100%;
            max-width: 680px;
            background: white;
            border-radius: 24px;
            padding: 40px;
            box-shadow: 0 24px 80px rgba(0,0,0,0.4);
            animation: slideIn 0.4s ease-out;
        }

        .quiz-header-bar {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 24px;
        }

        .quiz-logo {
            font-size: 22px;
            font-weight: 900;
            color: var(--primary);
            letter-spacing: -0.5px;
        }

        .q-counter {
            background: var(--primary-light);
            border: 1.5px solid var(--primary);
            border-radius: 50px;
            padding: 5px 16px;
            font-size: 13px;
            font-weight: 800;
            color: #444;
        }

        .progress-track {
            height: 8px;
            background: #f0f0f0;
            border-radius: 99px;
            margin-bottom: 28px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary-dark), var(--primary));
            border-radius: 99px;
            transition: width 0.4s ease;
        }

        .question-text {
            font-size: 20px;
            font-weight: 800;
            color: #1a1a2e;
            margin-bottom: 24px;
            line-height: 1.45;
        }

        .question-num {
            font-size: 12px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: #aaa;
            margin-bottom: 8px;
        }

        .option-btn {
            display: block;
            width: 100%;
            text-align: left;
            padding: 15px 20px;
            border: 2px solid #e8e8e8;
            border-radius: 12px;
            background: #fafafa;
            font-size: 15px;
            font-weight: 600;
            font-family: inherit;
            color: #333;
            cursor: pointer;
            margin-bottom: 12px;
            transition: 0.18s;
            position: relative;
        }

        .option-btn:hover:not(:disabled) {
            border-color: var(--primary);
            background: var(--primary-light);
            transform: translateX(4px);
        }

        .option-btn.selected {
            border-color: var(--primary);
            background: var(--primary-light);
        }

        .option-btn.correct {
            border-color: var(--success) !important;
            background: #e8f5e9 !important;
            color: #1b5e20 !important;
        }

        .option-btn.correct::after {
            content: ' ✓';
            font-weight: 900;
            color: var(--success);
        }

        .option-btn.incorrect {
            border-color: var(--danger) !important;
            background: #ffebee !important;
            color: #b71c1c !important;
        }

        .option-btn.incorrect::after {
            content: ' ✗';
            font-weight: 900;
            color: var(--danger);
        }

        .option-btn:disabled { cursor: default; }

        .feedback-box {
            margin-top: 16px;
            padding: 14px 18px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 15px;
            display: none;
        }

        .feedback-box.show { display: block; animation: feedbackIn 0.3s ease; }

        @keyframes feedbackIn {
            from { opacity: 0; transform: scale(0.96); }
            to { opacity: 1; transform: scale(1); }
        }

        .feedback-box.correct-fb {
            background: #e8f5e9;
            color: #1b5e20;
            border: 1.5px solid #81c784;
        }

        .feedback-box.incorrect-fb {
            background: #ffebee;
            color: #b71c1c;
            border: 1.5px solid #e57373;
        }

        .btn-next-q {
            width: 100%;
            padding: 14px;
            background: var(--dark);
            color: var(--primary);
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 20px;
            transition: 0.2s;
            letter-spacing: 0.3px;
        }

        .btn-next-q:hover { background: #2d2d50; transform: translateY(-2px); }
        .btn-next-q:disabled { background: #ccc; color: #888; cursor: not-allowed; transform: none; }

        /* Result */
        .result-screen { text-align: center; padding: 20px 0; }
        .score-circle {
            width: 140px; height: 140px;
            border-radius: 50%;
            background: conic-gradient(var(--primary) var(--pct, 0%), #f0f0f0 0%);
            display: flex; align-items: center; justify-content: center;
            margin: 0 auto 20px;
            position: relative;
            box-shadow: 0 8px 32px rgba(180,210,0,0.25);
        }

        .score-circle-inner {
            width: 112px; height: 112px;
            background: white;
            border-radius: 50%;
            display: flex; flex-direction: column;
            align-items: center; justify-content: center;
        }

        .score-num {
            font-size: 32px;
            font-weight: 900;
            color: var(--dark);
            line-height: 1;
        }

        .score-total { font-size: 13px; color: #aaa; font-weight: 700; }

        .result-emoji { font-size: 48px; margin-bottom: 10px; }
        .result-msg { font-size: 20px; font-weight: 800; color: #333; }
        .result-sub { font-size: 15px; color: #888; margin-top: 8px; }

        .btn-retry {
            display: inline-block;
            padding: 12px 32px;
            background: var(--primary);
            color: #333;
            border: none;
            border-radius: 50px;
            font-size: 15px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 24px;
            margin-right: 10px;
            transition: 0.2s;
        }

        .btn-retry:hover { background: var(--primary-dark); transform: translateY(-2px); }

        .btn-home {
            display: inline-block;
            padding: 12px 32px;
            background: var(--dark);
            color: var(--primary);
            border: none;
            border-radius: 50px;
            font-size: 15px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 24px;
            transition: 0.2s;
        }

        .btn-home:hover { background: #2d2d50; transform: translateY(-2px); }

        /* Toast */
        .toast-msg {
            position: fixed;
            top: 20px; right: 20px;
            background: #222;
            color: #fff;
            padding: 14px 22px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 14px;
            z-index: 9999;
            transform: translateX(200px);
            opacity: 0;
            transition: 0.3s;
            max-width: 300px;
        }

        .toast-msg.show { transform: translateX(0); opacity: 1; }
        .toast-msg.success { border-left: 4px solid var(--primary); }
        .toast-msg.error { border-left: 4px solid var(--danger); }

        @media (max-width: 600px) {
            .auth-box, .quiz-box { padding: 28px 20px; }
            .question-text { font-size: 17px; }
        }
         .math-bg {
    position: fixed;
    inset: 0;
    overflow: hidden;
    z-index: -1;
}

.math-bg span {
    position: absolute;
    color: rgba(0,0,0,0.1);
    font-weight: bold;
    animation: float 10s linear infinite;
    text-shadow: 
        0 0 2px rgba(0,0,0,0.3),
        0 0 6px rgba(0,0,0,0.2);
}

@keyframes float {
    from {
        transform: translateY(100vh);
        opacity: 1;
    }
    to {
        transform: translateY(-10vh);
        opacity: 1;
    }
}
    </style>
</head>
<body>
<div class="math-bg"></div>
<!-- TOAST -->
<div class="toast-msg" id="toast"></div>

<!-- ===== PAGE: ĐĂNG NHẬP ===== -->
<div id="page-login" class="page active">
    <div class="auth-page">
        <div class="auth-box">
            <div class="auth-logo">
                <h1>MinhEdu</h1>
                <p>Đăng nhập vào tài khoản của bạn</p>
            </div>
            <div class="form-field">
                <label>Email</label>
                <input type="email" id="login-email" placeholder="Nhập email của bạn">
                <span class="err-msg" id="login-email-err"></span>
            </div>
            <div class="form-field">
                <label>Mật khẩu</label>
                <input type="password" id="login-password" placeholder="Nhập mật khẩu" onkeydown="if(event.key==='Enter') doLogin()">
                <span class="err-msg" id="login-pass-err"></span>
            </div>
            <button class="btn-primary-auth" onclick="doLogin()">Đăng nhập</button>
            <div class="auth-footer">
                <p>Chưa có tài khoản? <a onclick="showPage('page-register')">Đăng ký ngay</a></p>
                <a onclick="showPage('page-main')">← Vào xem trang chính</a>
            </div>
        </div>
    </div>
</div>

<!-- ===== PAGE: ĐĂNG KÝ ===== -->
<div id="page-register" class="page">
    <div class="auth-page">
        <div class="auth-box">
            <div class="auth-logo">
                <h1>MinhEdu</h1>
                <p>Tạo tài khoản mới</p>
            </div>
            <div class="form-field">
                <label>Họ và tên</label>
                <input type="text" id="reg-name" placeholder="Nguyễn Văn A">
                <span class="err-msg" id="reg-name-err"></span>
            </div>
            <div class="form-field">
                <label>Email</label>
                <input type="email" id="reg-email" placeholder="email@example.com">
                <span class="err-msg" id="reg-email-err"></span>
            </div>
            <div class="form-field">
                <label>Mật khẩu</label>
                <input type="password" id="reg-pass" placeholder="Tối thiểu 6 ký tự">
                <span class="err-msg" id="reg-pass-err"></span>
            </div>
            <div class="form-field">
                <label>Xác nhận mật khẩu</label>
                <input type="password" id="reg-confirm" placeholder="Nhập lại mật khẩu" onkeydown="if(event.key==='Enter') doRegister()">
                <span class="err-msg" id="reg-confirm-err"></span>
            </div>
            <button class="btn-primary-auth" onclick="doRegister()">Đăng ký</button>
            <div class="auth-footer">
                <p>Đã có tài khoản? <a onclick="showPage('page-login')">Đăng nhập</a></p>
                <a onclick="showPage('page-main')">← Vào xem trang chính</a>
            </div>
        </div>
    </div>
</div>

<!-- ===== PAGE: TRANG CHÍNH ===== -->
<div id="page-main" class="page">
    <header class="header-top">
        <div class="container d-flex justify-content-between align-items-center">
            <div class="d-flex align-items-center gap-3">
                <div style="font-weight:900;font-size:22px;color:var(--dark);letter-spacing:-0.5px;">MinhEdu</div>
                <div class="search-box">
                    <i class="fas fa-search" style="color:#bbb;font-size:13px;"></i>
                    <input type="text" placeholder="Tìm kiếm bài học...">
                </div>
            </div>
            <div class="d-flex align-items-center gap-2" id="header-auth-area">
                <button class="btn btn-dark rounded-pill px-4 fw-bold" style="font-size:14px;" onclick="showPage('page-login')">Đăng nhập</button>
                <button class="btn rounded-pill px-4 fw-bold" style="background:var(--primary);font-size:14px;" onclick="showPage('page-register')">Đăng ký</button>
            </div>
        </div>
    </header>

    <nav class="navbar-custom">
        <div class="container">
            <div class="navbar-nav-custom">
                <a href="MinhEdu_Vaohoc.html"  class="active">Vào học</a>
                <a href="MinhEdu_Nhatkyhoctap.html">Nhật ký học tập</a>
                <a href="MinhEdu_Doiqua.html">Đổi quà</a>
                <a href="MinhEdu_ThanhTich.html">Thành tích</a>
                <a href="MinhEdu_MuaKhoaHoc.html">Mua khóa học</a>
            </div>
        </div>
    </nav>

    <main class="container mt-4 pb-5">
        <!-- Subject tabs -->
        <div class="d-flex gap-3 mb-4 overflow-auto pb-2">
            <div class="subject-card active" onclick="selectSubject(this)">
                <img src="https://cdn-icons-png.flaticon.com/512/2344/2344132.png" class="subject-icon" alt="Toán">
                <div class="fw-bold" style="font-size:13px;">Toán</div>
            </div>
            <div class="subject-card" onclick="selectSubject(this)">
                <img src="https://cdn-icons-png.flaticon.com/512/3771/3771278.png" class="subject-icon" alt="Toán TA">
                <div class="fw-bold" style="font-size:13px;">Toán Tiếng Anh</div>
            </div>
            <div class="subject-card" onclick="selectSubject(this)">
                <img src="https://cdn-icons-png.flaticon.com/512/2436/2436874.png" class="subject-icon" alt="Lý">
                <div class="fw-bold" style="font-size:13px;">Vật lý</div>
            </div>
            <div class="subject-card" onclick="selectSubject(this)">
                <img src="https://cdn-icons-png.flaticon.com/512/2942/2942909.png" class="subject-icon" alt="Hóa">
                <div class="fw-bold" style="font-size:13px;">Hóa học</div>
            </div>
        </div>

        <div class="row g-4">
            <!-- Sidebar -->
            <div class="col-md-4">
                <div class="sidebar-title">📚 Học kỳ 1 &nbsp;|&nbsp; Học kỳ 2</div>
                <div class="lesson-container">
                    <input type="text" class="form-control rounded-pill mb-3" placeholder="🔍 Tìm nhanh kỹ năng...">
                    <div class="lesson-item highlight" onclick="selectLesson(this, 'Đơn thức nhiều biến')">
                        <div class="fw-bold" style="font-size:14px;">Đơn thức nhiều biến. Đa thức nhiều biến</div>
                        <small class="text-muted">Số chủ điểm: 2 | Số bài KT: 5</small>
                    </div>
                    <div class="lesson-item" onclick="selectLesson(this, 'Phép cộng trừ đơn thức')">
                        <div class="fw-bold" style="font-size:14px;">Phép cộng, trừ đơn thức, đa thức nhiều biến</div>
                        <small class="text-muted">Số chủ điểm: 4 | Số bài KT: 1</small>
                    </div>
                    <div class="lesson-item" onclick="selectLesson(this, 'Phân tích nhân tử')">
                        <div class="fw-bold" style="font-size:14px;">Phân tích đa thức thành nhân tử</div>
                        <small class="text-muted">Số chủ điểm: 3 | Số bài KT: 2</small>
                    </div>
                    <div class="lesson-item" onclick="selectLesson(this, 'Hằng đẳng thức')">
                        <div class="fw-bold" style="font-size:14px;">Hằng đẳng thức đáng nhớ</div>
                        <small class="text-muted">Số chủ điểm: 7 | Số bài KT: 3</small>
                    </div>
                </div>
            </div>

            <!-- Main content -->
            <div class="col-md-8">
                <div class="d-flex justify-content-between align-items-center mb-3">
                    <h5 class="fw-bold mb-0" style="font-size:17px;">📋 Danh sách chủ điểm</h5>
                    <div class="d-flex gap-2">
                        <select class="form-select rounded-pill" style="font-size:13px;width:auto;">
                            <option>Lớp 8</option>
                            <option>Lớp 7</option>
                            <option>Lớp 9</option>
                        </select>
                        <select class="form-select rounded-pill" style="font-size:13px;width:auto;">
                            <option>Chân trời sáng tạo</option>
                            <option>Kết nối tri thức</option>
                        </select>
                    </div>
                </div>

                <div class="topic-header">
                    <div class="d-flex align-items-center justify-content-between">
                        <span class="fw-bold" id="topic-title">Đơn thức nhiều biến. Đa thức nhiều biến</span>
                        <span class="badge bg-light text-dark border fw-bold">0%</span>
                    </div>
                    <div class="d-flex flex-wrap gap-3 mt-3" style="font-size:13px;">
                        <div class="d-flex align-items-center gap-1">
                            <i class="fa-regular fa-circle text-secondary"></i> Chưa thực hành
                        </div>
                        <div class="d-flex align-items-center gap-1">
                            <i class="fa-solid fa-circle-notch text-info"></i> Đang thực hành
                        </div>
                        <div class="d-flex align-items-center gap-1">
                            <i class="fa-regular fa-circle-check text-success"></i> Đã hoàn thành
                        </div>
                        <div class="d-flex align-items-center gap-1">
                            <i class="fa-solid fa-circle-exclamation text-danger"></i> Cần ôn lại
                        </div>
                    </div>
                </div>

                <div class="row g-3">
                    <div class="col-sm-6">
                        <div class="grid-card" onclick="startQuiz('Đơn thức nhiều biến')">
                            <div class="card-icon">📐</div>
                            <div class="card-title">Đơn thức nhiều biến</div>
                            <div class="card-sub">5 câu hỏi · ~5 phút</div>
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="grid-card" onclick="startQuiz('Đa thức nhiều biến')">
                            <div class="card-icon">📊</div>
                            <div class="card-title">Đa thức nhiều biến</div>
                            <div class="card-sub">5 câu hỏi · ~5 phút</div>
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="grid-card" onclick="startQuiz('Phép cộng trừ đa thức')">
                            <div class="card-icon">➕</div>
                            <div class="card-title">Phép cộng, trừ đa thức</div>
                            <div class="card-sub">4 câu hỏi · ~4 phút</div>
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="grid-card" onclick="startQuiz('Hằng đẳng thức')">
                            <div class="card-icon">⚡</div>
                            <div class="card-title">Hằng đẳng thức đáng nhớ</div>
                            <div class="card-sub">5 câu hỏi · ~6 phút</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</div>

<!-- ===== PAGE: QUIZ ===== -->
<div id="page-quiz" class="page">
    <div class="quiz-page">
        <div class="quiz-box">
            <!-- Quiz header -->
            <div class="quiz-header-bar">
                <span class="quiz-logo">MinhEdu</span>
                <span class="q-counter" id="q-counter">1 / 5</span>
            </div>

            <!-- Progress -->
            <div class="progress-track">
                <div class="progress-fill" id="q-progress" style="width:0%;"></div>
            </div>

            <!-- Question area -->
            <div id="quiz-question-area">
                <div class="question-num" id="q-num">CÂU HỎI 1</div>
                <div class="question-text" id="q-text"></div>
                <div id="q-options"></div>
                <div class="feedback-box" id="q-feedback"></div>
                <button class="btn-next-q" id="btn-next" onclick="nextQuestion()" disabled>Câu tiếp theo →</button>
            </div>

            <!-- Result area (hidden) -->
            <div id="quiz-result-area" style="display:none;">
                <div class="result-screen">
                    <div class="score-circle" id="score-circle">
                        <div class="score-circle-inner">
                            <div class="score-num" id="result-score">0/5</div>
                            <div class="score-total" id="result-pct">0%</div>
                        </div>
                    </div>
                    <div class="result-emoji" id="result-emoji">🎉</div>
                    <div class="result-msg" id="result-msg">Xuất sắc!</div>
                    <div class="result-sub" id="result-sub">Bạn đã hoàn thành bài tập</div>
                    <div>
                        <button class="btn-retry" onclick="retryQuiz()">🔄 Làm lại</button>
                        <button class="btn-home" onclick="showPage('page-main')">🏠 Trang chủ</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

<script>
// ============================
// DATA
// ============================
const ALL_QUESTIONS = {
    'Đơn thức nhiều biến': [
        { q: "Đơn thức là gì?", opts: ["Biểu thức chứa phép cộng, trừ", "Tích của các số và các biến với số mũ nguyên dương", "Biểu thức có nhiều biến", "Phương trình bậc hai"], ans: 1 },
        { q: "Bậc của đơn thức 3x²y³ là bao nhiêu?", opts: ["2", "3", "5", "6"], ans: 2 },
        { q: "Đơn thức nào sau đây có bậc là 4?", opts: ["5x³y²", "2x²y²", "3xy", "7y²"], ans: 1 },
        { q: "Hệ số của đơn thức -7x²y là bao nhiêu?", opts: ["7", "-7", "2", "-2"], ans: 1 },
        { q: "Đơn thức đồng dạng với 3x²y là đơn thức nào?", opts: ["-5x²y", "3xy²", "3x²", "5xy"], ans: 0 }
    ],
    'Đa thức nhiều biến': [
        { q: "Đa thức là gì?", opts: ["Tích của các đơn thức", "Tổng của các đơn thức", "Hiệu của các đơn thức", "Thương của các đơn thức"], ans: 1 },
        { q: "Bậc của đa thức 3x²y + 2xy³ - 5 là?", opts: ["2", "3", "4", "5"], ans: 2 },
        { q: "Đa thức x² + 2xy + y² có bao nhiêu hạng tử?", opts: ["1", "2", "3", "4"], ans: 2 },
        { q: "Thu gọn đa thức: 3x² + 2x - x² + 5 bằng?", opts: ["2x² + 2x + 5", "4x² + 2x + 5", "2x² - 2x + 5", "3x² + 2x + 5"], ans: 0 },
        { q: "Hạng tử tự do trong đa thức 2x² + 3x - 7 là?", opts: ["2", "3", "-7", "0"], ans: 2 }
    ],
    'Phép cộng trừ đa thức': [
        { q: "2x + 3x bằng?", opts: ["5", "5x", "6x", "x"], ans: 1 },
        { q: "(2x + 3) - (x + 1) bằng?", opts: ["x + 2", "2x + 2", "3x + 4", "x - 2"], ans: 0 },
        { q: "(x² + 2x) + (3x² - x + 1) bằng?", opts: ["4x² + x + 1", "4x² + 3x + 1", "2x² + x + 1", "4x² - x + 1"], ans: 0 },
        { q: "Kết quả của (5x - 3) - (2x + 4) là?", opts: ["3x - 7", "3x + 1", "7x - 7", "3x - 1"], ans: 0 }
    ],
    'Hằng đẳng thức': [
        { q: "(a + b)² bằng?", opts: ["a² + b²", "a² + 2ab + b²", "a² - 2ab + b²", "a² + ab + b²"], ans: 1 },
        { q: "(a - b)² bằng?", opts: ["a² - b²", "a² + 2ab + b²", "a² - 2ab + b²", "a² - ab + b²"], ans: 2 },
        { q: "(a + b)(a - b) bằng?", opts: ["a² + b²", "a² - b²", "a² + 2ab - b²", "a² - 2ab + b²"], ans: 1 },
        { q: "(a + b)³ bằng?", opts: ["a³ + b³", "a³ + 3a²b + 3ab² + b³", "a³ - 3a²b + 3ab² - b³", "a³ + 3ab + b³"], ans: 1 },
        { q: "a³ - b³ bằng?", opts: ["(a-b)(a²+ab+b²)", "(a-b)(a²-ab+b²)", "(a+b)(a²-ab+b²)", "(a-b)³"], ans: 0 }
    ]
};

// ============================
// STATE
// ============================
let currentUser = null;
let quizState = {
    topic: '',
    questions: [],
    current: 0,
    score: 0,
    answered: false
};

// ============================
// INIT
// ============================
window.addEventListener('load', () => {
    const saved = localStorage.getItem('minhedu_user');
    if (saved) {
        currentUser = JSON.parse(saved);
        updateHeaderForUser();
        showPage('page-main');
    } else {
        showPage('page-login');
    }
});

// ============================
// PAGE NAV
// ============================
function showPage(id) {
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    window.scrollTo(0, 0);
}

// ============================
// AUTH
// ============================
function getUsers() {
    return JSON.parse(localStorage.getItem('minhedu_users') || '[]');
}

function saveUsers(users) {
    localStorage.setItem('minhedu_users', JSON.stringify(users));
}

function doLogin() {
    clearErrors(['login-email-err', 'login-pass-err']);
    const email = document.getElementById('login-email').value.trim();
    const pass = document.getElementById('login-password').value;

    let ok = true;
    if (!email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) {
        document.getElementById('login-email-err').textContent = 'Email không hợp lệ';
        ok = false;
    }
    if (pass.length < 6) {
        document.getElementById('login-pass-err').textContent = 'Mật khẩu phải ít nhất 6 ký tự';
        ok = false;
    }
    if (!ok) return;

    const users = getUsers();
    const user = users.find(u => u.email === email && u.password === pass);

    if (!user) {
        document.getElementById('login-pass-err').textContent = 'Email hoặc mật khẩu không chính xác';
        return;
    }

    currentUser = { id: user.id, name: user.name, email: user.email };
    localStorage.setItem('minhedu_user', JSON.stringify(currentUser));
    showToast('Chào mừng trở lại, ' + user.name + '! 👋', 'success');
    updateHeaderForUser();
    document.getElementById('login-email').value = '';
    document.getElementById('login-password').value = '';
    showPage('page-main');
}

function doRegister() {
    clearErrors(['reg-name-err', 'reg-email-err', 'reg-pass-err', 'reg-confirm-err']);
    const name = document.getElementById('reg-name').value.trim();
    const email = document.getElementById('reg-email').value.trim();
    const pass = document.getElementById('reg-pass').value;
    const confirm = document.getElementById('reg-confirm').value;

    let ok = true;
    if (name.length < 3) { document.getElementById('reg-name-err').textContent = 'Tên phải ít nhất 3 ký tự'; ok = false; }
    if (!email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) { document.getElementById('reg-email-err').textContent = 'Email không hợp lệ'; ok = false; }
    if (pass.length < 6) { document.getElementById('reg-pass-err').textContent = 'Mật khẩu phải ít nhất 6 ký tự'; ok = false; }
    if (pass !== confirm) { document.getElementById('reg-confirm-err').textContent = 'Mật khẩu không khớp'; ok = false; }
    if (!ok) return;

    const users = getUsers();
    if (users.find(u => u.email === email)) {
        document.getElementById('reg-email-err').textContent = 'Email đã được đăng ký!';
        return;
    }

    const newUser = { id: Date.now(), name, email, password: pass };
    users.push(newUser);
    saveUsers(users);

    currentUser = { id: newUser.id, name: newUser.name, email: newUser.email };
    localStorage.setItem('minhedu_user', JSON.stringify(currentUser));
    showToast('Đăng ký thành công! Chào mừng, ' + name + '! 🎉', 'success');
    updateHeaderForUser();
    document.getElementById('reg-name').value = '';
    document.getElementById('reg-email').value = '';
    document.getElementById('reg-pass').value = '';
    document.getElementById('reg-confirm').value = '';
    showPage('page-main');
}

function doLogout() {
    currentUser = null;
    localStorage.removeItem('minhedu_user');
    showToast('Đã đăng xuất', 'success');
    updateHeaderForUser();
}

function updateHeaderForUser() {
    const area = document.getElementById('header-auth-area');
    if (currentUser) {
        const initial = currentUser.name.charAt(0).toUpperCase();
        area.innerHTML = `
            <div class="user-chip">
                <div class="avatar">${initial}</div>
                <span>${currentUser.name}</span>
            </div>
            <button class="btn-logout" onclick="doLogout()">Đăng xuất</button>
        `;
    } else {
        area.innerHTML = `
            <button class="btn btn-dark rounded-pill px-4 fw-bold" style="font-size:14px;" onclick="showPage('page-login')">Đăng nhập</button>
            <button class="btn rounded-pill px-4 fw-bold" style="background:var(--primary);font-size:14px;" onclick="showPage('page-register')">Đăng ký</button>
        `;
    }
}

// ============================
// QUIZ
// ============================
function startQuiz(topic) {
    if (!currentUser) {
        showToast('Vui lòng đăng nhập để làm bài tập! 🔐', 'error');
        setTimeout(() => showPage('page-login'), 1200);
        return;
    }

    const qs = ALL_QUESTIONS[topic] || ALL_QUESTIONS['Đơn thức nhiều biến'];

    quizState = {
        topic,
        questions: shuffle([...qs]),
        current: 0,
        score: 0,
        answered: false
    };

    document.getElementById('quiz-question-area').style.display = 'block';
    document.getElementById('quiz-result-area').style.display = 'none';
    renderQuestion();
    showPage('page-quiz');
}

function renderQuestion() {
    const { questions, current } = quizState;
    const total = questions.length;
    const q = questions[current];

    document.getElementById('q-num').textContent = `CÂU HỎI ${current + 1}`;
    document.getElementById('q-counter').textContent = `${current + 1} / ${total}`;
    document.getElementById('q-text').textContent = q.q;
    document.getElementById('q-progress').style.width = ((current) / total * 100) + '%';

    const optContainer = document.getElementById('q-options');
    optContainer.innerHTML = q.opts.map((o, i) => `
        <button class="option-btn" onclick="selectAnswer(${i})" id="opt-${i}">${String.fromCharCode(65 + i)}. ${o}</button>
    `).join('');

    const fb = document.getElementById('q-feedback');
    fb.className = 'feedback-box';
    fb.innerHTML = '';

    document.getElementById('btn-next').disabled = true;
    document.getElementById('btn-next').textContent = current === total - 1 ? '🏁 Xem kết quả' : 'Câu tiếp theo →';
    quizState.answered = false;
}

function selectAnswer(idx) {
    if (quizState.answered) return;
    quizState.answered = true;

    const q = quizState.questions[quizState.current];
    const correct = q.ans;
    const opts = document.querySelectorAll('.option-btn');

    opts.forEach(b => b.disabled = true);
    opts.forEach((b, i) => {
        b.classList.remove('selected', 'correct', 'incorrect');
        if (i === correct) b.classList.add('correct');
        else if (i === idx) b.classList.add('incorrect');
    });

    const fb = document.getElementById('q-feedback');
    if (idx === correct) {
        quizState.score++;
        fb.className = 'feedback-box correct-fb show';
        fb.innerHTML = '✅ Chính xác! Bạn đã trả lời đúng.';
    } else {
        fb.className = 'feedback-box incorrect-fb show';
        fb.innerHTML = `❌ Sai rồi! Đáp án đúng là: <strong>${String.fromCharCode(65 + correct)}. ${q.opts[correct]}</strong>`;
    }

    document.getElementById('btn-next').disabled = false;
}

function nextQuestion() {
    if (!quizState.answered) {
        showToast('Hãy chọn một đáp án!', 'error');
        return;
    }
    quizState.current++;
    if (quizState.current < quizState.questions.length) {
        renderQuestion();
    } else {
        showResult();
    }
}

function showResult() {
    document.getElementById('quiz-question-area').style.display = 'none';
    document.getElementById('quiz-result-area').style.display = 'block';

    const { score, questions } = quizState;
    const total = questions.length;
    const pct = Math.round(score / total * 100);

    document.getElementById('result-score').textContent = score + '/' + total;
    document.getElementById('result-pct').textContent = pct + '%';

    // Animate circle
    const circle = document.getElementById('score-circle');
    circle.style.setProperty('--pct', pct + '%');

    let emoji, msg, sub;
    if (pct >= 90) { emoji = '🏆'; msg = 'Xuất sắc!'; sub = 'Kết quả tuyệt vời, tiếp tục phát huy nhé!'; }
    else if (pct >= 70) { emoji = '🎉'; msg = 'Giỏi lắm!'; sub = 'Bạn đã nắm khá vững kiến thức này!'; }
    else if (pct >= 50) { emoji = '👍'; msg = 'Khá tốt!'; sub = 'Ôn thêm một chút là hoàn hảo rồi!'; }
    else { emoji = '💪'; msg = 'Chưa tốt lắm!'; sub = 'Đừng nản, hãy làm lại để cải thiện điểm số!'; }

    document.getElementById('result-emoji').textContent = emoji;
    document.getElementById('result-msg').textContent = msg;
    document.getElementById('result-sub').textContent = sub;

    // Update progress
    document.getElementById('q-progress').style.width = '100%';
    document.getElementById('q-counter').textContent = quizState.questions.length + ' / ' + quizState.questions.length;
}

function retryQuiz() {
    startQuiz(quizState.topic);
}

// ============================
// UI HELPERS
// ============================
function selectSubject(el) {
    document.querySelectorAll('.subject-card').forEach(c => c.classList.remove('active'));
    el.classList.add('active');
}

function selectLesson(el, title) {
    document.querySelectorAll('.lesson-item').forEach(i => i.classList.remove('highlight'));
    el.classList.add('highlight');
    document.getElementById('topic-title').textContent = title;
}

function clearErrors(ids) {
    ids.forEach(id => {
        const el = document.getElementById(id);
        if (el) el.textContent = '';
    });
}

function showToast(msg, type = 'success') {
    const t = document.getElementById('toast');
    t.textContent = msg;
    t.className = 'toast-msg ' + type + ' show';
    setTimeout(() => t.className = 'toast-msg', 3000);
}

function shuffle(arr) {
    for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
    }
    return arr;
}
const LESSON_EXERCISES = {
    'Đơn thức nhiều biến': `
        <div class="col-sm-6">
            <div class="grid-card" onclick="startQuiz('Đơn thức nhiều biến')">
                <div class="card-icon">📐</div>
                <div class="card-title">Đơn thức nhiều biến</div>
                <div class="card-sub">5 câu hỏi · ~5 phút</div>
            </div>
        </div>

        <div class="col-sm-6">
            <div class="grid-card" onclick="startQuiz('Đa thức nhiều biến')">
                <div class="card-icon">📊</div>
                <div class="card-title">Đa thức nhiều biến</div>
                <div class="card-sub">5 câu hỏi · ~5 phút</div>
            </div>
        </div>
    `,

    'Phép cộng trừ đơn thức': `
        <div class="col-sm-6">
            <div class="grid-card" onclick="startQuiz('Phép cộng trừ đa thức')">
                <div class="card-icon">➕</div>
                <div class="card-title">Phép cộng trừ đa thức</div>
                <div class="card-sub">4 câu hỏi · ~4 phút</div>
            </div>
        </div>
    `,

    'Phân tích nhân tử': `
        <div class="col-sm-6">
            <div class="grid-card">
                <div class="card-icon">🧩</div>
                <div class="card-title">Phân tích đa thức thành nhân tử</div>
                <div class="card-sub">5 câu hỏi · ~5 phút</div>
            </div>
        </div>
    `,

    'Hằng đẳng thức': `
        <div class="col-sm-6">
            <div class="grid-card" onclick="startQuiz('Hằng đẳng thức')">
                <div class="card-icon">⚡</div>
                <div class="card-title">Hằng đẳng thức đáng nhớ</div>
                <div class="card-sub">5 câu hỏi · ~6 phút</div>
            </div>
        </div>
    `
};

const oldSelectLesson = selectLesson;

selectLesson = function(el, title){
    oldSelectLesson(el, title);

    const container = document.querySelector(".row.g-3");

    if(LESSON_EXERCISES[title]){
        container.innerHTML = LESSON_EXERCISES[title];
    }
}
const formulas = ["x²", "y=ax+b", "π", "√", "∑", "∫", "sin", "cos", "tan", "cot", "1+1=2", "3/4 - 7/8"];
const container = document.querySelector(".math-bg");

for (let i = 0; i < 100; i++) {
    let span = document.createElement("span");
    span.innerText = formulas[Math.floor(Math.random()*formulas.length)];

    span.style.left = Math.random()*100 + "vw";
    span.style.fontSize = (20 + Math.random()*30) + "px";
    span.style.animationDuration = (4 + Math.random()*4) + "s";
    span.style.animationDelay = Math.random() * 4 + "s";

    container.appendChild(span);
}
setInterval(() => {
    let span = document.createElement("span");
    span.innerText = formulas[Math.floor(Math.random()*formulas.length)];

    span.style.left = Math.random()*100 + "vw";
    span.style.fontSize = (20 + Math.random()*30) + "px";
    span.style.animationDuration = (6 + Math.random()*6) + "s";
    span.style.animationDelay = "0s";

    container.appendChild(span);

    // Xóa sau khi bay xong để tránh lag
    setTimeout(() => {
        span.remove();
    }, 10000);

}, 300);

</script>
</body>
</html>
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MinhEdu - Học tập chủ động</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #d4e815;
            --primary-dark: #b8cc00;
            --primary-light: #f1f8a4;
            --dark: #1a1a2e;
            --mid: #333;
            --bg: #f5f7f0;
            --white: #ffffff;
            --danger: #e53935;
            --success: #43a047;
            --info: #039be5;
            --radius: 16px;
            --shadow: 0 8px 32px rgba(0,0,0,0.10);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }

        body {
            font-family: 'Nunito', sans-serif;
            background: var(--bg);
            min-height: 100vh;
        }

        /* ===== PAGE SYSTEM ===== */
        .page { display: none; }
        .page.active { display: block; }

        /* ===== AUTH PAGES ===== */
        .auth-page {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 20px;
        }

        .auth-box {
            background: white;
            border-radius: 24px;
            padding: 44px 40px;
            width: 100%;
            max-width: 420px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.25);
            animation: slideIn 0.4s ease-out;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(-24px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .auth-logo {
            text-align: center;
            margin-bottom: 28px;
        }

        .auth-logo h1 {
            font-size: 36px;
            font-weight: 900;
            color: var(--primary);
            letter-spacing: -1px;
            text-shadow: 2px 3px 0 #c4d800;
        }

        .auth-logo p {
            color: #888;
            font-size: 15px;
            margin-top: 4px;
        }

        .form-field {
            margin-bottom: 18px;
        }

        .form-field label {
            display: block;
            margin-bottom: 7px;
            font-weight: 700;
            font-size: 14px;
            color: #444;
        }

        .form-field input {
            width: 100%;
            padding: 13px 16px;
            border: 2px solid #e5e5e5;
            border-radius: 12px;
            font-size: 15px;
            font-family: inherit;
            transition: 0.2s;
            background: #fafafa;
            color: #222;
        }

        .form-field input:focus {
            outline: none;
            border-color: var(--primary);
            background: white;
            box-shadow: 0 0 0 4px rgba(212,232,21,0.15);
        }

        .err-msg {
            display: block;
            color: var(--danger);
            font-size: 12px;
            font-weight: 600;
            margin-top: 5px;
            min-height: 16px;
        }

        .btn-primary-auth {
            width: 100%;
            padding: 14px;
            background: var(--primary);
            color: #222;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 800;
            cursor: pointer;
            transition: 0.2s;
            margin-top: 6px;
            letter-spacing: 0.3px;
        }

        .btn-primary-auth:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(180,210,0,0.35);
        }

        .auth-footer {
            text-align: center;
            margin-top: 22px;
            padding-top: 20px;
            border-top: 1px solid #eee;
        }

        .auth-footer p { color: #777; font-size: 14px; margin-bottom: 8px; }

        .auth-footer a {
            color: #764ba2;
            font-weight: 700;
            text-decoration: none;
            cursor: pointer;
        }

        .auth-footer a:hover { text-decoration: underline; }

        /* ===== MAIN APP ===== */
        #page-main { display: none; flex-direction: column; min-height: 100vh; }
        #page-main.active { display: flex; }

        .header-top {
            background: white;
            padding: 12px 0;
            border-bottom: 1px solid #eee;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        }

        .search-box {
            border: 1.5px solid #ddd;
            border-radius: 50px;
            padding: 7px 16px;
            display: flex;
            align-items: center;
            max-width: 280px;
            background: #fafafa;
        }

        .search-box input {
            border: none;
            outline: none;
            background: transparent;
            width: 100%;
            margin-left: 8px;
            font-size: 14px;
            font-family: inherit;
        }

        .user-chip {
            display: flex;
            align-items: center;
            gap: 8px;
            background: var(--primary-light);
            border: 1.5px solid var(--primary);
            border-radius: 50px;
            padding: 6px 16px 6px 10px;
            font-weight: 700;
            font-size: 14px;
            color: #333;
        }

        .user-chip .avatar {
            width: 28px; height: 28px;
            background: var(--primary);
            border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            font-weight: 900; font-size: 13px;
        }

        .btn-logout {
            background: #f0f0f0;
            border: none;
            border-radius: 50px;
            padding: 7px 18px;
            font-size: 13px;
            font-weight: 700;
            cursor: pointer;
            color: #555;
            transition: 0.2s;
        }

        .btn-logout:hover { background: #e0e0e0; color: #333; }

        .navbar-custom {
            background: var(--dark);
            padding: 0;
            overflow-x: auto;
        }

        .navbar-custom::-webkit-scrollbar { height: 3px; }
        .navbar-custom::-webkit-scrollbar-thumb { background: var(--primary); }

        .navbar-nav-custom {
            display: flex;
            white-space: nowrap;
            padding: 0 16px;
        }

        .navbar-nav-custom a {
            color: rgba(255,255,255,0.75) !important;
            font-weight: 700;
            padding: 13px 18px !important;
            text-transform: uppercase;
            font-size: 12px;
            letter-spacing: 0.5px;
            text-decoration: none;
            display: inline-block;
            transition: 0.2s;
            border-bottom: 3px solid transparent;
        }

        .navbar-nav-custom a:hover,
        .navbar-nav-custom a.active {
            color: var(--primary) !important;
            border-bottom-color: var(--primary);
        }

        /* Subject cards */
        .subject-card {
            background: white;
            border-radius: 14px;
            padding: 14px 20px;
            text-align: center;
            border: 2px solid #eee;
            cursor: pointer;
            transition: 0.2s;
            min-width: 110px;
        }

        .subject-card:hover { border-color: var(--primary); box-shadow: 0 4px 12px rgba(0,0,0,0.08); }
        .subject-card.active { border-color: var(--dark); background: var(--primary-light); }
        .subject-icon { width: 38px; margin-bottom: 8px; }

        /* Sidebar */
        .sidebar-title {
            background: var(--dark);
            color: var(--primary);
            padding: 14px 18px;
            border-radius: 14px 14px 0 0;
            font-weight: 800;
            font-size: 14px;
            letter-spacing: 0.3px;
        }

        .lesson-container {
            background: white;
            border-radius: 0 0 14px 14px;
            padding: 14px;
            min-height: 380px;
            box-shadow: var(--shadow);
        }

        .lesson-item {
            background: #f9f9f9;
            border: 1.5px solid #eee;
            border-radius: 12px;
            padding: 12px 14px;
            margin-bottom: 10px;
            cursor: pointer;
            transition: 0.2s;
        }

        .lesson-item:hover { border-color: var(--primary); }
        .lesson-item.highlight { background: var(--primary-light); border-color: var(--primary); }

        /* Topic & cards */
        .topic-header {
            background: white;
            border-radius: 14px;
            padding: 20px;
            border: 1.5px solid #eee;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
        }

        .grid-card {
            background: linear-gradient(135deg, #ffe082 0%, #ffca28 100%);
            border-radius: 16px;
            padding: 28px 20px;
            cursor: pointer;
            transition: 0.25s;
            box-shadow: 0 4px 16px rgba(255,200,0,0.2);
            border: 2px solid transparent;
            height: 100%;
        }

        .grid-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 12px 32px rgba(255,180,0,0.3);
            border-color: var(--primary-dark);
        }

        .grid-card .card-title {
            font-weight: 800;
            font-size: 16px;
            color: #333;
            margin-bottom: 6px;
        }

        .grid-card .card-sub {
            font-size: 13px;
            color: #666;
        }

        .grid-card .card-icon {
            font-size: 28px;
            margin-bottom: 10px;
        }

        /* ===== QUIZ PAGE ===== */
        .quiz-page {
            min-height: 100vh;
            background: linear-gradient(160deg, #1a1a2e 0%, #16213e 60%, #0f3460 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 24px;
        }

        .quiz-box {
            width: 100%;
            max-width: 680px;
            background: white;
            border-radius: 24px;
            padding: 40px;
            box-shadow: 0 24px 80px rgba(0,0,0,0.4);
            animation: slideIn 0.4s ease-out;
        }

        .quiz-header-bar {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 24px;
        }

        .quiz-logo {
            font-size: 22px;
            font-weight: 900;
            color: var(--primary);
            letter-spacing: -0.5px;
        }

        .q-counter {
            background: var(--primary-light);
            border: 1.5px solid var(--primary);
            border-radius: 50px;
            padding: 5px 16px;
            font-size: 13px;
            font-weight: 800;
            color: #444;
        }

        .progress-track {
            height: 8px;
            background: #f0f0f0;
            border-radius: 99px;
            margin-bottom: 28px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary-dark), var(--primary));
            border-radius: 99px;
            transition: width 0.4s ease;
        }

        .question-text {
            font-size: 20px;
            font-weight: 800;
            color: #1a1a2e;
            margin-bottom: 24px;
            line-height: 1.45;
        }

        .question-num {
            font-size: 12px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: #aaa;
            margin-bottom: 8px;
        }

        .option-btn {
            display: block;
            width: 100%;
            text-align: left;
            padding: 15px 20px;
            border: 2px solid #e8e8e8;
            border-radius: 12px;
            background: #fafafa;
            font-size: 15px;
            font-weight: 600;
            font-family: inherit;
            color: #333;
            cursor: pointer;
            margin-bottom: 12px;
            transition: 0.18s;
            position: relative;
        }

        .option-btn:hover:not(:disabled) {
            border-color: var(--primary);
            background: var(--primary-light);
            transform: translateX(4px);
        }

        .option-btn.selected {
            border-color: var(--primary);
            background: var(--primary-light);
        }

        .option-btn.correct {
            border-color: var(--success) !important;
            background: #e8f5e9 !important;
            color: #1b5e20 !important;
        }

        .option-btn.correct::after {
            content: ' ✓';
            font-weight: 900;
            color: var(--success);
        }

        .option-btn.incorrect {
            border-color: var(--danger) !important;
            background: #ffebee !important;
            color: #b71c1c !important;
        }

        .option-btn.incorrect::after {
            content: ' ✗';
            font-weight: 900;
            color: var(--danger);
        }

        .option-btn:disabled { cursor: default; }

        .feedback-box {
            margin-top: 16px;
            padding: 14px 18px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 15px;
            display: none;
        }

        .feedback-box.show { display: block; animation: feedbackIn 0.3s ease; }

        @keyframes feedbackIn {
            from { opacity: 0; transform: scale(0.96); }
            to { opacity: 1; transform: scale(1); }
        }

        .feedback-box.correct-fb {
            background: #e8f5e9;
            color: #1b5e20;
            border: 1.5px solid #81c784;
        }

        .feedback-box.incorrect-fb {
            background: #ffebee;
            color: #b71c1c;
            border: 1.5px solid #e57373;
        }

        .btn-next-q {
            width: 100%;
            padding: 14px;
            background: var(--dark);
            color: var(--primary);
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 20px;
            transition: 0.2s;
            letter-spacing: 0.3px;
        }

        .btn-next-q:hover { background: #2d2d50; transform: translateY(-2px); }
        .btn-next-q:disabled { background: #ccc; color: #888; cursor: not-allowed; transform: none; }

        /* Result */
        .result-screen { text-align: center; padding: 20px 0; }
        .score-circle {
            width: 140px; height: 140px;
            border-radius: 50%;
            background: conic-gradient(var(--primary) var(--pct, 0%), #f0f0f0 0%);
            display: flex; align-items: center; justify-content: center;
            margin: 0 auto 20px;
            position: relative;
            box-shadow: 0 8px 32px rgba(180,210,0,0.25);
        }

        .score-circle-inner {
            width: 112px; height: 112px;
            background: white;
            border-radius: 50%;
            display: flex; flex-direction: column;
            align-items: center; justify-content: center;
        }

        .score-num {
            font-size: 32px;
            font-weight: 900;
            color: var(--dark);
            line-height: 1;
        }

        .score-total { font-size: 13px; color: #aaa; font-weight: 700; }

        .result-emoji { font-size: 48px; margin-bottom: 10px; }
        .result-msg { font-size: 20px; font-weight: 800; color: #333; }
        .result-sub { font-size: 15px; color: #888; margin-top: 8px; }

        .btn-retry {
            display: inline-block;
            padding: 12px 32px;
            background: var(--primary);
            color: #333;
            border: none;
            border-radius: 50px;
            font-size: 15px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 24px;
            margin-right: 10px;
            transition: 0.2s;
        }

        .btn-retry:hover { background: var(--primary-dark); transform: translateY(-2px); }

        .btn-home {
            display: inline-block;
            padding: 12px 32px;
            background: var(--dark);
            color: var(--primary);
            border: none;
            border-radius: 50px;
            font-size: 15px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 24px;
            transition: 0.2s;
        }

        .btn-home:hover { background: #2d2d50; transform: translateY(-2px); }

        /* Toast */
        .toast-msg {
            position: fixed;
            top: 20px; right: 20px;
            background: #222;
            color: #fff;
            padding: 14px 22px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 14px;
            z-index: 9999;
            transform: translateX(200px);
            opacity: 0;
            transition: 0.3s;
            max-width: 300px;
        }

        .toast-msg.show { transform: translateX(0); opacity: 1; }
        .toast-msg.success { border-left: 4px solid var(--primary); }
        .toast-msg.error { border-left: 4px solid var(--danger); }

        @media (max-width: 600px) {
            .auth-box, .quiz-box { padding: 28px 20px; }
            .question-text { font-size: 17px; }
        }
        body{
        background:#f7f7f7;

        }

        /* HEADER */

        .topbar{
        background:#ffc107;
        color:white;
        padding:10px;
        font-weight:600;
        }

        /* TITLE */

        .title{
        text-align:center;
        margin:30px 0 20px;
        font-weight:700;
        }

        /* TAB */

        .tabs{
        display:flex;
        justify-content:center;
        gap:10px;
        margin-bottom:20px;
        }

        .tab-btn{
        border:none;
        padding:10px 25px;
        border-radius:20px;
        background:#ddd;
        font-weight:600;
        cursor:pointer;
        }

        .tab-btn.active{
        background:#ffc107;
        color:white;
        }

        /* DIAMOND */

        .diamond-box{
        text-align:center;
        background:white;
        border-radius:15px;
        padding:20px;
        margin-bottom:25px;
        }

        .diamond{
        font-size:26px;
        font-weight:700;
        color:#ff9800;
        }

        /* CARD QUÀ */

        .gift-card{
        background:white;
        border-radius:15px;
        padding:20px;
        text-align:center;
        transition:.2s;
        border:2px solid transparent;
        }

        .gift-card:hover{
        border-color:#ffc107;
        transform:translateY(-5px);
        }

        .gift-img{
        font-size:40px;
        margin-bottom:10px;
        }

        .exchange-btn{
        background:#ffc107;
        border:none;
        color:white;
        padding:8px 18px;
        border-radius:20px;
        margin-top:10px;
        }

        .exchange-btn:hover{
        background:#ffb300;
        }
.math-bg {
    position: fixed;
    inset: 0;
    overflow: hidden;
    z-index: -1;
}

.math-bg span {
    position: absolute;
    opacity: 0.15; /* giảm rối mắt */
    animation: float 12s linear infinite;
    pointer-events: none;
}

@keyframes float {
    from {
        transform: translateY(100vh);
        opacity: 1;
    }
    to {
        transform: translateY(-10vh);
        opacity: 1;
    }
}
    </style>
</head>
<body>
<div class="math-bg"></div>
<!-- TOAST -->
<div class="toast-msg" id="toast"></div>

<!-- ===== PAGE: ĐĂNG NHẬP ===== -->
<div id="page-login" class="page active">
    <div class="auth-page">
        <div class="auth-box">
            <div class="auth-logo">
                <h1>MinhEdu</h1>
                <p>Đăng nhập vào tài khoản của bạn</p>
            </div>
            <div class="form-field">
                <label>Email</label>
                <input type="email" id="login-email" placeholder="Nhập email của bạn">
                <span class="err-msg" id="login-email-err"></span>
            </div>
            <div class="form-field">
                <label>Mật khẩu</label>
                <input type="password" id="login-password" placeholder="Nhập mật khẩu" onkeydown="if(event.key==='Enter') doLogin()">
                <span class="err-msg" id="login-pass-err"></span>
            </div>
            <button class="btn-primary-auth" onclick="doLogin()">Đăng nhập</button>
            <div class="auth-footer">
                <p>Chưa có tài khoản? <a onclick="showPage('page-register')">Đăng ký ngay</a></p>
                <a onclick="showPage('page-main')">← Vào xem trang chính</a>
            </div>
        </div>
    </div>
</div>

<!-- ===== PAGE: ĐĂNG KÝ ===== -->
<div id="page-register" class="page">
    <div class="auth-page">
        <div class="auth-box">
            <div class="auth-logo">
                <h1>MinhEdu</h1>
                <p>Tạo tài khoản mới</p>
            </div>
            <div class="form-field">
                <label>Họ và tên</label>
                <input type="text" id="reg-name" placeholder="Nguyễn Văn A">
                <span class="err-msg" id="reg-name-err"></span>
            </div>
            <div class="form-field">
                <label>Email</label>
                <input type="email" id="reg-email" placeholder="email@example.com">
                <span class="err-msg" id="reg-email-err"></span>
            </div>
            <div class="form-field">
                <label>Mật khẩu</label>
                <input type="password" id="reg-pass" placeholder="Tối thiểu 6 ký tự">
                <span class="err-msg" id="reg-pass-err"></span>
            </div>
            <div class="form-field">
                <label>Xác nhận mật khẩu</label>
                <input type="password" id="reg-confirm" placeholder="Nhập lại mật khẩu" onkeydown="if(event.key==='Enter') doRegister()">
                <span class="err-msg" id="reg-confirm-err"></span>
            </div>
            <button class="btn-primary-auth" onclick="doRegister()">Đăng ký</button>
            <div class="auth-footer">
                <p>Đã có tài khoản? <a onclick="showPage('page-login')">Đăng nhập</a></p>
                <a onclick="showPage('page-main')">← Vào xem trang chính</a>
            </div>
        </div>
    </div>
</div>

<!-- ===== PAGE: TRANG CHÍNH ===== -->
<div id="page-main" class="page">
    <header class="header-top">
        <div class="container d-flex justify-content-between align-items-center">
            <div class="d-flex align-items-center gap-3">
                <div style="font-weight:900;font-size:22px;color:var(--dark);letter-spacing:-0.5px;">MinhEdu</div>
                <div class="search-box">
                    <i class="fas fa-search" style="color:#bbb;font-size:13px;"></i>
                    <input type="text" placeholder="Tìm kiếm bài học...">
                </div>
            </div>
            <div class="d-flex align-items-center gap-2" id="header-auth-area">
                <button class="btn btn-dark rounded-pill px-4 fw-bold" style="font-size:14px;" onclick="showPage('page-login')">Đăng nhập</button>
                <button class="btn rounded-pill px-4 fw-bold" style="background:var(--primary);font-size:14px;" onclick="showPage('page-register')">Đăng ký</button>
            </div>
        </div>
    </header>

    <nav class="navbar-custom">
        <div class="container">
            <div class="navbar-nav-custom">
                <a href="MinhEdu_Vaohoc.html">Vào học</a>
                <a href="MinhEdu_Nhatkyhoctap.html">Nhật ký học tập</a>
                <a href="MinhEdu_Doiqua.html" class="active">Đổi quà</a>
                <a href="MinhEdu_ThanhTich.html">Thành tích</a>
                <a href="MinhEdu_MuaKhoaHoc.html">Mua khóa học</a>
            </div>
        </div>
    </nav>

<div class="container">

    <h3 class="title">Gian hàng đổi thưởng</h3>

    <!-- TABS -->
    <div class="tabs">
        <button class="tab-btn active" onclick="showTab('hienvat')">Quà hiện vật</button>
        <button class="tab-btn" onclick="showTab('voucher')">Voucher khóa học</button>
        <button class="tab-btn" onclick="showTab('event')">Sự kiện kỳ thú</button>
    </div>

    <!-- DIAMOND -->
    <div class="diamond-box">
        <div>💎</div>
        <div class="diamond">263</div>
        <p>Có cày có thóc, có học được quà!</p>
    </div>

    <!-- QUÀ HIỆN VẬT -->
    <div id="hienvat" class="gift-section">
        <div class="row g-4">
            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">📘</div>
                    <h6>Sách Toán nâng cao</h6>
                    <p>300 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">✏️</div>
                    <h6>Bút cao cấp</h6>
                    <p>120 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">📒</div>
                    <h6>Sổ tay học tập</h6>
                    <p>150 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🧴</div>
                    <h6>Bình nước</h6>
                    <p>180 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">⌚</div>
                    <h6>Đồng hồ điện tử</h6>
                    <p>600 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🎧</div>
                    <h6>Tai nghe</h6>
                    <p>450 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🖱️</div>
                    <h6>Chuột máy tính</h6>
                    <p>250 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">⌨️</div>
                    <h6>Bàn phím mini</h6>
                    <p>350 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">📱</div>
                    <h6>Giá đỡ điện thoại</h6>
                    <p>130 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">💡</div>
                    <h6>Đèn học chống cận</h6>
                    <p>400 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🎮</div>
                    <h6>Tay cầm chơi game</h6>
                    <p>550 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🧠</div>
                    <h6>Khóa học tư duy</h6>
                    <p>700 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">📦</div>
                    <h6>Hộp quà bí ẩn</h6>
                    <p>350 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🎁</div>
                    <h6>Combo học tập</h6>
                    <p>800 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🏆</div>
                    <h6>Huy chương vàng</h6>
                    <p>1000 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>
        </div>
    </div>

    <!-- VOUCHER -->
    <div id="voucher" class="gift-section" style="display:none">
        <div class="row g-4">

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">📐</div>
                    <h6>Voucher Hình học</h6>
                    <p>350 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🧮</div>
                    <h6>Voucher Đại số</h6>
                    <p>380 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">📊</div>
                    <h6>Voucher Thống kê</h6>
                    <p>300 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🧠</div>
                    <h6>Voucher Tư duy logic</h6>
                    <p>450 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🌍</div>
                    <h6>Voucher Tiếng Anh</h6>
                    <p>400 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">💻</div>
                    <h6>Voucher Tin học</h6>
                    <p>320 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">⚗️</div>
                    <h6>Voucher Hóa học</h6>
                    <p>370 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🔬</div>
                    <h6>Voucher Sinh học</h6>
                    <p>340 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🌌</div>
                    <h6>Voucher Vật lý</h6>
                    <p>390 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">📖</div>
                    <h6>Voucher Văn học</h6>
                    <p>280 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🏛️</div>
                    <h6>Voucher Lịch sử</h6>
                    <p>260 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🌏</div>
                    <h6>Voucher Địa lý</h6>
                    <p>250 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🎯</div>
                    <h6>Voucher luyện đề</h6>
                    <p>420 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🔥</div>
                    <h6>Voucher cấp tốc</h6>
                    <p>500 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">👑</div>
                    <h6>Voucher VIP</h6>
                    <p>900 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🎁</div>
                    <h6>Voucher ngẫu nhiên</h6>
                    <p>350 💎</p>
                    <button class="exchange-btn">Đổi quà</button>
                </div>
            </div>
        </div>
    </div>

    <!-- EVENT -->
    <div id="event" class="gift-section" style="display:none">
        <div class="row g-4">

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">⚔️</div>
                    <h6>Đấu PvP 1vs1</h6>
                    <p>250 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🏆</div>
                    <h6>Giải đấu tuần</h6>
                    <p>300 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🔥</div>
                    <h6>Thử thách siêu tốc</h6>
                    <p>180 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🧠</div>
                    <h6>Đấu trí IQ</h6>
                    <p>220 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🎲</div>
                    <h6>Vòng quay may mắn</h6>
                    <p>150 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">💣</div>
                    <h6>Chế độ sinh tồn</h6>
                    <p>280 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🚀</div>
                    <h6>Leo rank thần tốc</h6>
                    <p>260 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🎮</div>
                    <h6>Mini game học tập</h6>
                    <p>140 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">📚</div>
                    <h6>Marathon 24h học</h6>
                    <p>350 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">👑</div>
                    <h6>Thử thách VIP</h6>
                    <p>500 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">⚡</div>
                    <h6>Blitz quiz 1 phút</h6>
                    <p>120 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🌟</div>
                    <h6>Event điểm thưởng x2</h6>
                    <p>200 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🎤</div>
                    <h6>Đố vui trực tiếp</h6>
                    <p>210 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🕹️</div>
                    <h6>Game học tương tác</h6>
                    <p>170 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🎯</div>
                    <h6>Thử thách chính xác</h6>
                    <p>190 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

            <div class="col-md-3">
                <div class="gift-card">
                    <div class="gift-img">🎁</div>
                    <h6>Sự kiện bí mật</h6>
                    <p>300 💎</p>
                    <button class="exchange-btn">Tham gia</button>
                </div>
            </div>

        </div>
    </div>

</div>
<script>
// ============================
// DATA
// ============================


// ============================
// STATE
// ============================
let currentUser = null;
let quizState = {
    topic: '',
    questions: [],
    current: 0,
    score: 0,
    answered: false
};

// ============================
// INIT
// ============================
window.addEventListener('load', () => {
    const saved = localStorage.getItem('minhedu_user');
    if (saved) {
        currentUser = JSON.parse(saved);
        updateHeaderForUser();
        showPage('page-main');
    } else {
        showPage('page-login');
    }
});

// ============================
// PAGE NAV
// ============================
function showPage(id) {
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    window.scrollTo(0, 0);
}

// ============================
// AUTH
// ============================
function getUsers() {
    return JSON.parse(localStorage.getItem('minhedu_users') || '[]');
}

function saveUsers(users) {
    localStorage.setItem('minhedu_users', JSON.stringify(users));
}

function doLogin() {
    clearErrors(['login-email-err', 'login-pass-err']);
    const email = document.getElementById('login-email').value.trim();
    const pass = document.getElementById('login-password').value;

    let ok = true;
    if (!email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) {
        document.getElementById('login-email-err').textContent = 'Email không hợp lệ';
        ok = false;
    }
    if (pass.length < 6) {
        document.getElementById('login-pass-err').textContent = 'Mật khẩu phải ít nhất 6 ký tự';
        ok = false;
    }
    if (!ok) return;

    const users = getUsers();
    const user = users.find(u => u.email === email && u.password === pass);

    if (!user) {
        document.getElementById('login-pass-err').textContent = 'Email hoặc mật khẩu không chính xác';
        return;
    }

    currentUser = { id: user.id, name: user.name, email: user.email };
    localStorage.setItem('minhedu_user', JSON.stringify(currentUser));
    showToast('Chào mừng trở lại, ' + user.name + '! 👋', 'success');
    updateHeaderForUser();
    document.getElementById('login-email').value = '';
    document.getElementById('login-password').value = '';
    showPage('page-main');
}

function doRegister() {
    clearErrors(['reg-name-err', 'reg-email-err', 'reg-pass-err', 'reg-confirm-err']);
    const name = document.getElementById('reg-name').value.trim();
    const email = document.getElementById('reg-email').value.trim();
    const pass = document.getElementById('reg-pass').value;
    const confirm = document.getElementById('reg-confirm').value;

    let ok = true;
    if (name.length < 3) { document.getElementById('reg-name-err').textContent = 'Tên phải ít nhất 3 ký tự'; ok = false; }
    if (!email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) { document.getElementById('reg-email-err').textContent = 'Email không hợp lệ'; ok = false; }
    if (pass.length < 6) { document.getElementById('reg-pass-err').textContent = 'Mật khẩu phải ít nhất 6 ký tự'; ok = false; }
    if (pass !== confirm) { document.getElementById('reg-confirm-err').textContent = 'Mật khẩu không khớp'; ok = false; }
    if (!ok) return;

    const users = getUsers();
    if (users.find(u => u.email === email)) {
        document.getElementById('reg-email-err').textContent = 'Email đã được đăng ký!';
        return;
    }

    const newUser = { id: Date.now(), name, email, password: pass };
    users.push(newUser);
    saveUsers(users);

    currentUser = { id: newUser.id, name: newUser.name, email: newUser.email };
    localStorage.setItem('minhedu_user', JSON.stringify(currentUser));
    showToast('Đăng ký thành công! Chào mừng, ' + name + '! 🎉', 'success');
    updateHeaderForUser();
    document.getElementById('reg-name').value = '';
    document.getElementById('reg-email').value = '';
    document.getElementById('reg-pass').value = '';
    document.getElementById('reg-confirm').value = '';
    showPage('page-main');
}

function doLogout() {
    currentUser = null;
    localStorage.removeItem('minhedu_user');
    showToast('Đã đăng xuất', 'success');
    updateHeaderForUser();
}

function updateHeaderForUser() {
    const area = document.getElementById('header-auth-area');
    if (currentUser) {
        const initial = currentUser.name.charAt(0).toUpperCase();
        area.innerHTML = `
            <div class="user-chip">
                <div class="avatar">${initial}</div>
                <span>${currentUser.name}</span>
            </div>
            <button class="btn-logout" onclick="doLogout()">Đăng xuất</button>
        `;
    } else {
        area.innerHTML = `
            <button class="btn btn-dark rounded-pill px-4 fw-bold" style="font-size:14px;" onclick="showPage('page-login')">Đăng nhập</button>
            <button class="btn rounded-pill px-4 fw-bold" style="background:var(--primary);font-size:14px;" onclick="showPage('page-register')">Đăng ký</button>
        `;
    }
}
function showTab(tab){

document.querySelectorAll('.gift-section')
.forEach(el => el.style.display='none')

document.getElementById(tab).style.display='block'

document.querySelectorAll('.tab-btn')
.forEach(btn => btn.classList.remove('active'))

event.target.classList.add('active')

}
const formulas = ["🎁", "🎀", "🛍️", "💎", "🏆", "🎯", "🎲", "👑", "🎧", "🎮", "📐", "🖱️", "⌨️", "✏️"]
const container = document.querySelector(".math-bg");

// spawn ban đầu (ít thôi)
for (let i = 0; i < 25; i++) {
    createItem();
}

// spawn liên tục nhưng chậm hơn
setInterval(createItem, 800);

function createItem() {
    let span = document.createElement("span");
    span.innerText = formulas[Math.floor(Math.random()*formulas.length)];

    span.style.left = Math.random()*100 + "vw";
    span.style.fontSize = (20 + Math.random()*20) + "px";
    span.style.animationDuration = (6 + Math.random()*4) + "s";

    container.appendChild(span);

    setTimeout(() => {
        span.remove();
    }, 10000);
}
</script>
</body>
</html>
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MinhEdu - Học tập chủ động</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #d4e815;
            --primary-dark: #b8cc00;
            --primary-light: #f1f8a4;
            --dark: #1a1a2e;
            --mid: #333;
            --bg: #f5f7f0;
            --white: #ffffff;
            --danger: #e53935;
            --success: #43a047;
            --info: #039be5;
            --radius: 16px;
            --shadow: 0 8px 32px rgba(0,0,0,0.10);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }

       body {
            font-family: 'Nunito', sans-serif;
            background: #f5f7f0;
            color: #333;
            
        }
        
        .section {
        padding: 30px;
        }
        h2 { margin-bottom: 20px; }

        /* COMMON CARD */
        .card {
        border-radius: 16px;
        padding: 20px;
        margin: 10px;
        display: inline-block;
        width: 200px;
        }

        /* ================= GAMING STYLE ================= */
        .gaming { background: linear-gradient(135deg,#1a1a1a,#000); }
        .gaming .card {
        background: #222;
        border: 2px solid gold;
        box-shadow: 0 0 15px gold;
        text-align: center;
        }

        /* ================= STUDY STYLE ================= */
        .study { background: #f5f5f5; color: black; }
        .study .card {
        background: white;
        border: 1px solid #ddd;
        }
        .progress {
        height: 10px;
        background: #ddd;
        border-radius: 10px;
        overflow: hidden;
        }
        .progress div {
        height: 100%;
        background: gold;
        width: 70%;
        }

        /* ================= MINIMAL STYLE ================= */
        .minimal { background: #fff; color: black; }
        .minimal .card {
        border: 1px solid #eee;
        transition: 0.3s;
        }
        .minimal .card:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }


        /* ===== PAGE SYSTEM ===== */
        .page { display: none; }
        .page.active { display: block; }

        /* ===== AUTH PAGES ===== */
        .auth-page {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 20px;
        }

        .auth-box {
            background: white;
            border-radius: 24px;
            padding: 44px 40px;
            width: 100%;
            max-width: 420px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.25);
            animation: slideIn 0.4s ease-out;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(-24px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .auth-logo {
            text-align: center;
            margin-bottom: 28px;
        }

        .auth-logo h1 {
            font-size: 36px;
            font-weight: 900;
            color: var(--primary);
            letter-spacing: -1px;
            text-shadow: 2px 3px 0 #c4d800;
        }

        .auth-logo p {
            color: #888;
            font-size: 15px;
            margin-top: 4px;
        }

        .form-field {
            margin-bottom: 18px;
        }

        .form-field label {
            display: block;
            margin-bottom: 7px;
            font-weight: 700;
            font-size: 14px;
            color: #444;
        }

        .form-field input {
            width: 100%;
            padding: 13px 16px;
            border: 2px solid #e5e5e5;
            border-radius: 12px;
            font-size: 15px;
            font-family: inherit;
            transition: 0.2s;
            background: #fafafa;
            color: #222;
        }

        .form-field input:focus {
            outline: none;
            border-color: var(--primary);
            background: white;
            box-shadow: 0 0 0 4px rgba(212,232,21,0.15);
        }

        .err-msg {
            display: block;
            color: var(--danger);
            font-size: 12px;
            font-weight: 600;
            margin-top: 5px;
            min-height: 16px;
        }

        .btn-primary-auth {
            width: 100%;
            padding: 14px;
            background: var(--primary);
            color: #222;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 800;
            cursor: pointer;
            transition: 0.2s;
            margin-top: 6px;
            letter-spacing: 0.3px;
        }

        .btn-primary-auth:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(180,210,0,0.35);
        }

        .auth-footer {
            text-align: center;
            margin-top: 22px;
            padding-top: 20px;
            border-top: 1px solid #eee;
        }

        .auth-footer p { color: #777; font-size: 14px; margin-bottom: 8px; }

        .auth-footer a {
            color: #764ba2;
            font-weight: 700;
            text-decoration: none;
            cursor: pointer;
        }

        .auth-footer a:hover { text-decoration: underline; }

        /* ===== MAIN APP ===== */
        #page-main { display: none; flex-direction: column; min-height: 100vh; }
        #page-main.active { display: flex; }

        .header-top {
            background: white;
            padding: 12px 0;
            border-bottom: 1px solid #eee;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        }

        .search-box {
            border: 1.5px solid #ddd;
            border-radius: 50px;
            padding: 7px 16px;
            display: flex;
            align-items: center;
            max-width: 280px;
            background: #fafafa;
        }

        .search-box input {
            border: none;
            outline: none;
            background: transparent;
            width: 100%;
            margin-left: 8px;
            font-size: 14px;
            font-family: inherit;
        }

        .user-chip {
            display: flex;
            align-items: center;
            gap: 8px;
            background: var(--primary-light);
            border: 1.5px solid var(--primary);
            border-radius: 50px;
            padding: 6px 16px 6px 10px;
            font-weight: 700;
            font-size: 14px;
            color: #333;
        }

        .user-chip .avatar {
            width: 28px; height: 28px;
            background: var(--primary);
            border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            font-weight: 900; font-size: 13px;
        }

        .btn-logout {
            background: #f0f0f0;
            border: none;
            border-radius: 50px;
            padding: 7px 18px;
            font-size: 13px;
            font-weight: 700;
            cursor: pointer;
            color: #555;
            transition: 0.2s;
        }

        .btn-logout:hover { background: #e0e0e0; color: #333; }

        .navbar-custom {
            background: var(--dark);
            padding: 0;
            overflow-x: auto;
        }

        .navbar-custom::-webkit-scrollbar { height: 3px; }
        .navbar-custom::-webkit-scrollbar-thumb { background: var(--primary); }

        .navbar-nav-custom {
            display: flex;
            white-space: nowrap;
            padding: 0 16px;
        }

        .navbar-nav-custom a {
            color: rgba(255,255,255,0.75) !important;
            font-weight: 700;
            padding: 13px 18px !important;
            text-transform: uppercase;
            font-size: 12px;
            letter-spacing: 0.5px;
            text-decoration: none;
            display: inline-block;
            transition: 0.2s;
            border-bottom: 3px solid transparent;
        }

        .navbar-nav-custom a:hover,
        .navbar-nav-custom a.active {
            color: var(--primary) !important;
            border-bottom-color: var(--primary);
        }

        /* Subject cards */
        .subject-card {
            background: white;
            border-radius: 14px;
            padding: 14px 20px;
            text-align: center;
            border: 2px solid #eee;
            cursor: pointer;
            transition: 0.2s;
            min-width: 110px;
        }

        .subject-card:hover { border-color: var(--primary); box-shadow: 0 4px 12px rgba(0,0,0,0.08); }
        .subject-card.active { border-color: var(--dark); background: var(--primary-light); }
        .subject-icon { width: 38px; margin-bottom: 8px; }

        /* Sidebar */
        .sidebar-title {
            background: var(--dark);
            color: var(--primary);
            padding: 14px 18px;
            border-radius: 14px 14px 0 0;
            font-weight: 800;
            font-size: 14px;
            letter-spacing: 0.3px;
        }

        .lesson-container {
            background: white;
            border-radius: 0 0 14px 14px;
            padding: 14px;
            min-height: 380px;
            box-shadow: var(--shadow);
        }

        .lesson-item {
            background: #f9f9f9;
            border: 1.5px solid #eee;
            border-radius: 12px;
            padding: 12px 14px;
            margin-bottom: 10px;
            cursor: pointer;
            transition: 0.2s;
        }

        .lesson-item:hover { border-color: var(--primary); }
        .lesson-item.highlight { background: var(--primary-light); border-color: var(--primary); }

        /* Topic & cards */
        .topic-header {
            background: white;
            border-radius: 14px;
            padding: 20px;
            border: 1.5px solid #eee;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
        }

        .grid-card {
            background: linear-gradient(135deg, #ffe082 0%, #ffca28 100%);
            border-radius: 16px;
            padding: 28px 20px;
            cursor: pointer;
            transition: 0.25s;
            box-shadow: 0 4px 16px rgba(255,200,0,0.2);
            border: 2px solid transparent;
            height: 100%;
        }

        .grid-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 12px 32px rgba(255,180,0,0.3);
            border-color: var(--primary-dark);
        }

        .grid-card .card-title {
            font-weight: 800;
            font-size: 16px;
            color: #333;
            margin-bottom: 6px;
        }

        .grid-card .card-sub {
            font-size: 13px;
            color: #666;
        }

        .grid-card .card-icon {
            font-size: 28px;
            margin-bottom: 10px;
        }

        /* ===== QUIZ PAGE ===== */
        .quiz-page {
            min-height: 100vh;
            background: linear-gradient(160deg, #1a1a2e 0%, #16213e 60%, #0f3460 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 24px;
        }

        .quiz-box {
            width: 100%;
            max-width: 680px;
            background: white;
            border-radius: 24px;
            padding: 40px;
            box-shadow: 0 24px 80px rgba(0,0,0,0.4);
            animation: slideIn 0.4s ease-out;
        }

        .quiz-header-bar {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 24px;
        }

        .quiz-logo {
            font-size: 22px;
            font-weight: 900;
            color: var(--primary);
            letter-spacing: -0.5px;
        }

        .q-counter {
            background: var(--primary-light);
            border: 1.5px solid var(--primary);
            border-radius: 50px;
            padding: 5px 16px;
            font-size: 13px;
            font-weight: 800;
            color: #444;
        }

        .progress-track {
            height: 8px;
            background: #f0f0f0;
            border-radius: 99px;
            margin-bottom: 28px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary-dark), var(--primary));
            border-radius: 99px;
            transition: width 0.4s ease;
        }

        .question-text {
            font-size: 20px;
            font-weight: 800;
            color: #1a1a2e;
            margin-bottom: 24px;
            line-height: 1.45;
        }

        .question-num {
            font-size: 12px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: #aaa;
            margin-bottom: 8px;
        }

        .option-btn {
            display: block;
            width: 100%;
            text-align: left;
            padding: 15px 20px;
            border: 2px solid #e8e8e8;
            border-radius: 12px;
            background: #fafafa;
            font-size: 15px;
            font-weight: 600;
            font-family: inherit;
            color: #333;
            cursor: pointer;
            margin-bottom: 12px;
            transition: 0.18s;
            position: relative;
        }

        .option-btn:hover:not(:disabled) {
            border-color: var(--primary);
            background: var(--primary-light);
            transform: translateX(4px);
        }

        .option-btn.selected {
            border-color: var(--primary);
            background: var(--primary-light);
        }

        .option-btn.correct {
            border-color: var(--success) !important;
            background: #e8f5e9 !important;
            color: #1b5e20 !important;
        }

        .option-btn.correct::after {
            content: ' ✓';
            font-weight: 900;
            color: var(--success);
        }

        .option-btn.incorrect {
            border-color: var(--danger) !important;
            background: #ffebee !important;
            color: #b71c1c !important;
        }

        .option-btn.incorrect::after {
            content: ' ✗';
            font-weight: 900;
            color: var(--danger);
        }

        .option-btn:disabled { cursor: default; }

        .feedback-box {
            margin-top: 16px;
            padding: 14px 18px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 15px;
            display: none;
        }

        .feedback-box.show { display: block; animation: feedbackIn 0.3s ease; }

        @keyframes feedbackIn {
            from { opacity: 0; transform: scale(0.96); }
            to { opacity: 1; transform: scale(1); }
        }

        .feedback-box.correct-fb {
            background: #e8f5e9;
            color: #1b5e20;
            border: 1.5px solid #81c784;
        }

        .feedback-box.incorrect-fb {
            background: #ffebee;
            color: #b71c1c;
            border: 1.5px solid #e57373;
        }

        .btn-next-q {
            width: 100%;
            padding: 14px;
            background: var(--dark);
            color: var(--primary);
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 20px;
            transition: 0.2s;
            letter-spacing: 0.3px;
        }

        .btn-next-q:hover { background: #2d2d50; transform: translateY(-2px); }
        .btn-next-q:disabled { background: #ccc; color: #888; cursor: not-allowed; transform: none; }

        /* Result */
        .result-screen { text-align: center; padding: 20px 0; }
        .score-circle {
            width: 140px; height: 140px;
            border-radius: 50%;
            background: conic-gradient(var(--primary) var(--pct, 0%), #f0f0f0 0%);
            display: flex; align-items: center; justify-content: center;
            margin: 0 auto 20px;
            position: relative;
            box-shadow: 0 8px 32px rgba(180,210,0,0.25);
        }

        .score-circle-inner {
            width: 112px; height: 112px;
            background: white;
            border-radius: 50%;
            display: flex; flex-direction: column;
            align-items: center; justify-content: center;
        }

        .score-num {
            font-size: 32px;
            font-weight: 900;
            color: var(--dark);
            line-height: 1;
        }

        .score-total { font-size: 13px; color: #aaa; font-weight: 700; }

        .result-emoji { font-size: 48px; margin-bottom: 10px; }
        .result-msg { font-size: 20px; font-weight: 800; color: #333; }
        .result-sub { font-size: 15px; color: #888; margin-top: 8px; }

        .btn-retry {
            display: inline-block;
            padding: 12px 32px;
            background: var(--primary);
            color: #333;
            border: none;
            border-radius: 50px;
            font-size: 15px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 24px;
            margin-right: 10px;
            transition: 0.2s;
        }

        .btn-retry:hover { background: var(--primary-dark); transform: translateY(-2px); }

        .btn-home {
            display: inline-block;
            padding: 12px 32px;
            background: var(--dark);
            color: var(--primary);
            border: none;
            border-radius: 50px;
            font-size: 15px;
            font-weight: 800;
            cursor: pointer;
            margin-top: 24px;
            transition: 0.2s;
        }

        .btn-home:hover { background: #2d2d50; transform: translateY(-2px); }

        /* Toast */
        .toast-msg {
            position: fixed;
            top: 20px; right: 20px;
            background: #222;
            color: #fff;
            padding: 14px 22px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 14px;
            z-index: 9999;
            transform: translateX(200px);
            opacity: 0;
            transition: 0.3s;
            max-width: 300px;
        }

        .toast-msg.show { transform: translateX(0); opacity: 1; }
        .toast-msg.success { border-left: 4px solid var(--primary); }
        .toast-msg.error { border-left: 4px solid var(--danger); }

        @media (max-width: 600px) {
            .auth-box, .quiz-box { padding: 28px 20px; }
            .question-text { font-size: 17px; }
        }
        .shelf-row {
            display: flex;
            gap: 20px;
            align-items: flex-end; /* QUAN TRỌNG: đứng trên kệ */
            position: relative;
            padding-bottom: 20px;
        }

        /* THANH GỖ */
        .shelf-row::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 10px;
            background: linear-gradient(90deg, #8b5a2b, #c49a6c);
            border-radius: 6px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
        }

        /* CUỐN SÁCH */
        .book {
            width: 90px;
            height: 130px;
            background: linear-gradient(180deg, #ffe082, #ffca28);
            border-radius: 6px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            font-weight: 700;
            font-size: 12px;
            text-align: center;
            color: #333;
            cursor: pointer;
            transition: 0.2s;
            position: relative;
        }

        /* GÁY SÁCH */
        .book::before {
            content: "";
            position: absolute;
            left: 0;
            top: 0;
            width: 6px;
            height: 100%;
            background: #e0b000;
            border-radius: 6px 0 0 6px;
        }

        .book i {
            font-size: 20px;
            margin-bottom: 6px;
        }

        /* HOVER */
        .book:hover {
            transform: translateY(-10px);
        }

        /* CHƯA MỞ */
        .book.locked {
            background: #ddd;
            color: #999;
        }

        .book.locked::before {
            background: #bbb;
        }
        /* ===== TAB MENU ===== */
        .achievement-tabs {
            display: flex;
            gap: 10px;
            margin: 20px;
        }

        .tab {
            padding: 10px 20px;
            background: #eee;
            border-radius: 10px;
            font-weight: 700;
            cursor: pointer;
            transition: 0.2s;
        }

        .tab:hover {
            background: #ddd;
        }

        .tab.active {
            background: linear-gradient(135deg, #ffe082, #ffca28);
            color: #333;
        }

        /* CONTENT BOX */
        .achievement-content {
            background: white;
            margin: 0 20px;
            padding: 20px;
            border-radius: 16px;
            box-shadow: var(--shadow);
        }
        .achievement-list {
            margin-top: 10px;
        }

        /* CARD */
        .achievement-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: #f5f5f5;
            border-radius: 12px;
            padding: 14px 18px;
            border: 1px solid #ddd;
            transition: 0.2s;
        }

        /* HOVER */
        .achievement-item:hover {
            background: #fff8dc;
            border-color: #f4c542;
        }

        /* ICON */
        .achievement-item i {
            font-size: 22px;
            color: #f4c542;
            margin-right: 12px;
        }

        /* TEXT */
        .achievement-item .content {
            flex: 1;
        }

        .achievement-item b {
            font-size: 15px;
        }

        .achievement-item p {
            margin: 0;
            font-size: 12px;
            color: #777;
        }

        /* BUTTON */
        .achievement-item button {
            background: white;
            border: 1px solid #ccc;
            border-radius: 20px;
            padding: 5px 14px;
            cursor: pointer;
        }

        /* LOCKED */
        .achievement-item.locked {
            opacity: 0.6;
        }

        .achievement-item.locked i {
            color: #aaa;
        }
        .math-bg {
    position: fixed;
    inset: 0;
    overflow: hidden;
    z-index: -1;
}

.math-bg span {
    position: absolute;
    color: rgba(0,0,0,0.1);
    font-weight: bold;
    animation: float 10s linear infinite;
    text-shadow: 
        0 0 2px rgba(0,0,0,0.3),
        0 0 6px rgba(0,0,0,0.2);
}

@keyframes float {
    from {
        transform: translateY(100vh);
        opacity: 1;
    }
    to {
        transform: translateY(-10vh);
        opacity: 1;
    }
}
    </style>
</head>
<body>
<div class="math-bg"></div>
<!-- TOAST -->
<div class="toast-msg" id="toast"></div>

<!-- ===== PAGE: ĐĂNG NHẬP ===== -->
<div id="page-login" class="page active">
    <div class="auth-page">
        <div class="auth-box">
            <div class="auth-logo">
                <h1>MinhEdu</h1>
                <p>Đăng nhập vào tài khoản của bạn</p>
            </div>
            <div class="form-field">
                <label>Email</label>
                <input type="email" id="login-email" placeholder="Nhập email của bạn">
                <span class="err-msg" id="login-email-err"></span>
            </div>
            <div class="form-field">
                <label>Mật khẩu</label>
                <input type="password" id="login-password" placeholder="Nhập mật khẩu" onkeydown="if(event.key==='Enter') doLogin()">
                <span class="err-msg" id="login-pass-err"></span>
            </div>
            <button class="btn-primary-auth" onclick="doLogin()">Đăng nhập</button>
            <div class="auth-footer">
                <p>Chưa có tài khoản? <a onclick="showPage('page-register')">Đăng ký ngay</a></p>
                <a onclick="showPage('page-main')">← Vào xem trang chính</a>
            </div>
        </div>
    </div>
</div>

<!-- ===== PAGE: ĐĂNG KÝ ===== -->
<div id="page-register" class="page">
    <div class="auth-page">
        <div class="auth-box">
            <div class="auth-logo">
                <h1>MinhEdu</h1>
                <p>Tạo tài khoản mới</p>
            </div>
            <div class="form-field">
                <label>Họ và tên</label>
                <input type="text" id="reg-name" placeholder="Nguyễn Văn A">
                <span class="err-msg" id="reg-name-err"></span>
            </div>
            <div class="form-field">
                <label>Email</label>
                <input type="email" id="reg-email" placeholder="email@example.com">
                <span class="err-msg" id="reg-email-err"></span>
            </div>
            <div class="form-field">
                <label>Mật khẩu</label>
                <input type="password" id="reg-pass" placeholder="Tối thiểu 6 ký tự">
                <span class="err-msg" id="reg-pass-err"></span>
            </div>
            <div class="form-field">
                <label>Xác nhận mật khẩu</label>
                <input type="password" id="reg-confirm" placeholder="Nhập lại mật khẩu" onkeydown="if(event.key==='Enter') doRegister()">
                <span class="err-msg" id="reg-confirm-err"></span>
            </div>
            <button class="btn-primary-auth" onclick="doRegister()">Đăng ký</button>
            <div class="auth-footer">
                <p>Đã có tài khoản? <a onclick="showPage('page-login')">Đăng nhập</a></p>
                <a onclick="showPage('page-main')">← Vào xem trang chính</a>
            </div>
        </div>
    </div>
</div>
<div id="page-main" class="page">
    <header class="header-top">
        <div class="container d-flex justify-content-between align-items-center">
            <div class="d-flex align-items-center gap-3">
                <div style="font-weight:900;font-size:22px;color:var(--dark);letter-spacing:-0.5px;">MinhEdu</div>
                <div class="search-box">
                    <i class="fas fa-search" style="color:#bbb;font-size:13px;"></i>
                    <input type="text" placeholder="Tìm kiếm bài học...">
                </div>
            </div>
            <div class="d-flex align-items-center gap-2" id="header-auth-area">
                <button class="btn btn-dark rounded-pill px-4 fw-bold" style="font-size:14px;" onclick="showPage('page-login')">Đăng nhập</button>
                <button class="btn rounded-pill px-4 fw-bold" style="background:var(--primary);font-size:14px;" onclick="showPage('page-register')">Đăng ký</button>
            </div>
        </div>
    </header>

    <nav class="navbar-custom">
        <div class="container">
            <div class="navbar-nav-custom">
                <a href="MinhEdu_Vaohoc.html">Vào học</a>
                <a href="MinhEdu_Nhatkyhoctap.html">Nhật ký học tập</a>
                <a href="MinhEdu_Doiqua.html">Đổi quà</a>
                <a href="MinhEdu_ThanhTich.html">Thành tích</a>
                <a href="MinhEdu_MuaKhoaHoc.html" class="active">Mua khóa học</a>
            </div>
        </div>
    </nav>

        <div class="container my-5">
            <div class="row justify-content-center">
                <div class="col-lg-10 bg-white shadow-sm p-4 rounded-4">
                    
                    <div class="section-account mb-5">
                        <h5 class="text-success fw-bold d-flex align-items-center mb-4">
                            <span class="badge bg-success rounded-circle me-2">01</span> Thông tin tài khoản
                        </h5>
                        <div class="row g-3">
                            <div class="col-md-6">
                                <label class="form-label fw-bold small">Họ và Tên <span class="text-danger">*</span></label>
                                <input type="text" class="form-control" value="Nguyễn Hoàng Gia Minh">
                            </div>
                            <div class="col-md-6">
                                <label class="form-label fw-bold small">Số điện thoại <span class="text-danger">*</span></label>
                                <input type="text" class="form-control" placeholder="Nhập số điện thoại">
                            </div>
                            <div class="col-md-6">
                                <label class="form-label fw-bold small">Email</label>
                                <input type="email" class="form-control" placeholder="Email liên hệ">
                            </div>
                            <div class="col-md-6">
                                <label class="form-label fw-bold small">Địa chỉ <span class="text-danger">*</span></label>
                                <input type="text" class="form-control" placeholder="Địa chỉ liên hệ">
                            </div>
                        </div>
                    </div>

                    <div class="section-packages">
                        <h5 class="text-success fw-bold d-flex align-items-center mb-4">
                            <span class="badge bg-success rounded-circle me-2">02</span> Lựa chọn gói học
                        </h5>

                        <!-- Banner thông báo -->
                        <div class="p-3 mb-4 border border-success rounded-3 bg-light d-flex justify-content-between align-items-center">
                            <div>
                                <i class="fa-solid fa-gift text-success me-2"></i>
                                <small>
                                    Tài khoản thuộc nhà trường được ưu đãi 10-35% khi mua khóa học.
                                </small>
                            </div>
                            <button class="btn btn-primary btn-sm rounded-pill">Liên hệ hỗ trợ</button>
                        </div>

                        <!-- Toggle -->
                        <div class="d-flex gap-3 mb-4">
                            <div class="flex-fill text-center p-3 border border-success rounded-3 bg-light fw-bold">
                                🎁 Mua theo combo
                            </div>
                            <div class="flex-fill text-center p-3 border rounded-3 text-muted fw-bold">
                                💎 Mua lẻ từng môn
                            </div>
                        </div>

                        <!-- Gói học -->
                        <div class="row g-4">

                            <!-- 6 tháng -->
                            <div class="col-md-6">
                                <div class="card w-100 p-4 rounded-4 shadow-sm border-2">

                                    <div class="d-flex justify-content-between align-items-center mb-3">
                                        <span class="fw-bold">GÓI HỌC 6 tháng</span>
                                        <span class="badge bg-warning text-dark">50 💎</span>
                                    </div>

                                    <ul class="small text-muted mb-4">
                                        <li>Được thách đấu 10 lượt/ngày</li>
                                        <li>Tặng 50 kim cương + 2 lượt thi thử</li>
                                    </ul>

                                    <div class="text-center">
                                        <div class="text-muted text-decoration-line-through">
                                            600.000 VNĐ
                                        </div>
                                        <div class="text-danger fw-bold fs-4">
                                            540.000 VNĐ
                                        </div>

                                        <button class="btn btn-success w-100 rounded-pill mt-3">
                                            Lựa chọn gói học
                                        </button>
                                    </div>

                                </div>
                            </div>

                            <!-- 12 tháng -->
                            <div class="col-md-6">
                                <div class="card w-100 p-4 rounded-4 shadow-sm border-2">

                                    <div class="d-flex justify-content-between align-items-center mb-3">
                                        <span class="fw-bold">GÓI HỌC 12 tháng</span>
                                        <span class="badge bg-info text-dark">100 💎</span>
                                    </div>

                                    <ul class="small text-muted mb-4">
                                        <li>Được thách đấu 25 lượt/ngày</li>
                                        <li>Tặng 100 kim cương + 5 lượt thi thử</li>
                                    </ul>

                                    <div class="text-center">
                                        <div class="text-muted text-decoration-line-through">
                                            960.000 VNĐ
                                        </div>
                                        <div class="text-danger fw-bold fs-4">
                                            816.000 VNĐ
                                        </div>

                                        <button class="btn btn-success w-100 rounded-pill mt-3">
                                            Lựa chọn gói học
                                        </button>
                                    </div>

                                </div>
                            </div>
                            <div class="col-md-6">
                                <div class="card w-100 p-4 rounded-4 shadow-sm border-2">

                                    <div class="d-flex justify-content-between align-items-center mb-3">
                                        <span class="fw-bold">GÓI HỌC 8 tháng</span>
                                        <span class="badge bg-warning text-dark">70 💎</span>
                                    </div>

                                    <ul class="small text-muted mb-4">
                                        <li>Được thách đấu 15 lượt/ngày</li>
                                        <li>Tặng 70 kim cương + 4 lượt thi thử</li>
                                    </ul>

                                    <div class="text-center">
                                        <div class="text-muted text-decoration-line-through">
                                            720.000 VNĐ
                                        </div>
                                        <div class="text-danger fw-bold fs-4">
                                            600.000 VNĐ
                                        </div>

                                        <button class="btn btn-success w-100 rounded-pill mt-3">
                                            Lựa chọn gói học
                                        </button>
                                    </div>

                                </div>
                            </div>

                            <!-- 3 tháng -->
                            <div class="col-md-6">
                                <div class="card w-100 p-4 rounded-4 shadow-sm border-2">

                                    <div class="d-flex justify-content-between align-items-center mb-3">
                                        <span class="fw-bold">GÓI HỌC 3 tháng</span>
                                        <span class="badge bg-info text-dark">25 💎</span>
                                    </div>

                                    <ul class="small text-muted mb-4">
                                        <li>Được thách đấu 5 lượt/ngày</li>
                                        <li>Tặng 25 kim cương + 2 lượt thi thử</li>
                                    </ul>

                                    <div class="text-center">
                                        <div class="text-muted text-decoration-line-through">
                                            360.000 VNĐ
                                        </div>
                                        <div class="text-danger fw-bold fs-4">
                                            315.000 VNĐ
                                        </div>

                                        <button class="btn btn-success w-100 rounded-pill mt-3">
                                            Lựa chọn gói học
                                        </button>
                                    </div>

                                </div>
                            </div>

                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>  
</div>

<script>

// ============================
// STATE
// ============================
let currentUser = null;
let quizState = {
    topic: '',
    questions: [],
    current: 0,
    score: 0,
    answered: false
};

// ============================
// INIT
// ============================
window.addEventListener('load', () => {
    const saved = localStorage.getItem('minhedu_user');
    if (saved) {
        currentUser = JSON.parse(saved);
        updateHeaderForUser();
        showPage('page-main');
    } else {
        showPage('page-login');
    }
});

// ============================
// PAGE NAV
// ============================
function showPage(id) {
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    window.scrollTo(0, 0);
}

// ============================
// AUTH
// ============================
function getUsers() {
    return JSON.parse(localStorage.getItem('minhedu_users') || '[]');
}

function saveUsers(users) {
    localStorage.setItem('minhedu_users', JSON.stringify(users));
}

function doLogin() {
    clearErrors(['login-email-err', 'login-pass-err']);
    const email = document.getElementById('login-email').value.trim();
    const pass = document.getElementById('login-password').value;

    let ok = true;
    if (!email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) {
        document.getElementById('login-email-err').textContent = 'Email không hợp lệ';
        ok = false;
    }
    if (pass.length < 6) {
        document.getElementById('login-pass-err').textContent = 'Mật khẩu phải ít nhất 6 ký tự';
        ok = false;
    }
    if (!ok) return;

    const users = getUsers();
    const user = users.find(u => u.email === email && u.password === pass);

    if (!user) {
        document.getElementById('login-pass-err').textContent = 'Email hoặc mật khẩu không chính xác';
        return;
    }

    currentUser = { id: user.id, name: user.name, email: user.email };
    localStorage.setItem('minhedu_user', JSON.stringify(currentUser));
    showToast('Chào mừng trở lại, ' + user.name + '! 👋', 'success');
    updateHeaderForUser();
    document.getElementById('login-email').value = '';
    document.getElementById('login-password').value = '';
    showPage('page-main');
}

function doRegister() {
    clearErrors(['reg-name-err', 'reg-email-err', 'reg-pass-err', 'reg-confirm-err']);
    const name = document.getElementById('reg-name').value.trim();
    const email = document.getElementById('reg-email').value.trim();
    const pass = document.getElementById('reg-pass').value;
    const confirm = document.getElementById('reg-confirm').value;

    let ok = true;
    if (name.length < 3) { document.getElementById('reg-name-err').textContent = 'Tên phải ít nhất 3 ký tự'; ok = false; }
    if (!email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) { document.getElementById('reg-email-err').textContent = 'Email không hợp lệ'; ok = false; }
    if (pass.length < 6) { document.getElementById('reg-pass-err').textContent = 'Mật khẩu phải ít nhất 6 ký tự'; ok = false; }
    if (pass !== confirm) { document.getElementById('reg-confirm-err').textContent = 'Mật khẩu không khớp'; ok = false; }
    if (!ok) return;

    const users = getUsers();
    if (users.find(u => u.email === email)) {
        document.getElementById('reg-email-err').textContent = 'Email đã được đăng ký!';
        return;
    }

    const newUser = { id: Date.now(), name, email, password: pass };
    users.push(newUser);
    saveUsers(users);

    currentUser = { id: newUser.id, name: newUser.name, email: newUser.email };
    localStorage.setItem('minhedu_user', JSON.stringify(currentUser));
    showToast('Đăng ký thành công! Chào mừng, ' + name + '! 🎉', 'success');
    updateHeaderForUser();
    document.getElementById('reg-name').value = '';
    document.getElementById('reg-email').value = '';
    document.getElementById('reg-pass').value = '';
    document.getElementById('reg-confirm').value = '';
    showPage('page-main');
}

function doLogout() {
    currentUser = null;
    localStorage.removeItem('minhedu_user');
    showToast('Đã đăng xuất', 'success');
    updateHeaderForUser();
}

function updateHeaderForUser() {
    const area = document.getElementById('header-auth-area');
    if (currentUser) {
        const initial = currentUser.name.charAt(0).toUpperCase();
        area.innerHTML = `
            <div class="user-chip">
                <div class="avatar">${initial}</div>
                <span>${currentUser.name}</span>
            </div>
            <button class="btn-logout" onclick="doLogout()">Đăng xuất</button>
        `;
    } else {
        area.innerHTML = `
            <button class="btn btn-dark rounded-pill px-4 fw-bold" style="font-size:14px;" onclick="showPage('page-login')">Đăng nhập</button>
            <button class="btn rounded-pill px-4 fw-bold" style="background:var(--primary);font-size:14px;" onclick="showPage('page-register')">Đăng ký</button>
        `;
    }
}
const formulas = ["x²", "y=ax+b", "π", "√", "∑", "∫", "sin", "cos", "tan", "cot", "1+1=2", "3/4 - 7/8"];
const container = document.querySelector(".math-bg");

for (let i = 0; i < 100; i++) {
    let span = document.createElement("span");
    span.innerText = formulas[Math.floor(Math.random()*formulas.length)];

    span.style.left = Math.random()*100 + "vw";
    span.style.fontSize = (20 + Math.random()*30) + "px";
    span.style.animationDuration = (4 + Math.random()*4) + "s";
    span.style.animationDelay = Math.random() * 4 + "s";

    container.appendChild(span);
}
setInterval(() => {
    let span = document.createElement("span");
    span.innerText = formulas[Math.floor(Math.random()*formulas.length)];

    span.style.left = Math.random()*100 + "vw";
    span.style.fontSize = (20 + Math.random()*30) + "px";
    span.style.animationDuration = (4 + Math.random()*4) + "s";
    span.style.animationDelay = "0s";

    container.appendChild(span);

    // Xóa sau khi bay xong để tránh lag
    setTimeout(() => {
        span.remove();
    }, 10000);

}, 100);

</script>
</body>
</html>
