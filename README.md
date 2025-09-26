<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pendaftaran Siswa Baru - SMKN 1 Purbalingga</title>
    
    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <!-- Bootstrap Icons -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.0/font/bootstrap-icons.css">
    <!-- Animate.css -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
    
    <style>
        :root {
            --primary-color: #1e3a8a;
            --secondary-color: #3b82f6;
            --accent-color: #f59e0b;
            --success-color: #10b981;
            --danger-color: #ef4444;
            --light-bg: #f8fafc;
        }

        body {
            background-color: var(--light-bg);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        /* Header Styles */
        .header-section {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            color: white;
            padding: 3rem 0;
            position: relative;
            overflow: hidden;
        }

        .header-section::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 500px;
            height: 500px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
        }

        .school-logo {
            width: 100px;
            height: 100px;
            background-color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1rem;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            position: relative;
            z-index: 1;
        }

        /* Form Container */
        .form-container {
            background: white;
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            padding: 2.5rem;
            margin: -3rem auto 3rem;
            position: relative;
            z-index: 2;
        }

        /* Section Styles */
        .form-section {
            margin-bottom: 2.5rem;
            padding-bottom: 2rem;
            border-bottom: 2px solid #e5e7eb;
            position: relative;
        }

        .form-section:last-child {
            border-bottom: none;
            margin-bottom: 0;
            padding-bottom: 0;
        }

        .section-title {
            color: var(--primary-color);
            font-weight: 600;
            margin-bottom: 1.5rem;
            padding-bottom: 0.75rem;
            border-bottom: 3px solid var(--secondary-color);
            display: inline-block;
            font-size: 1.25rem;
        }

        .section-title i {
            margin-right: 0.5rem;
        }

        /* Form Controls */
        .form-label {
            font-weight: 500;
            color: #374151;
            margin-bottom: 0.5rem;
        }

        .form-control, .form-select {
            border: 2px solid #e5e7eb;
            border-radius: 10px;
            padding: 0.75rem 1rem;
            transition: all 0.3s ease;
        }

        .form-control:focus, .form-select:focus {
            border-color: var(--secondary-color);
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
        }

        .form-control.is-invalid, .form-select.is-invalid {
            border-color: var(--danger-color);
        }

        /* Button Styles */
        .btn-primary {
            background-color: var(--primary-color);
            border-color: var(--primary-color);
            padding: 0.75rem 2rem;
            font-weight: 500;
            border-radius: 10px;
            transition: all 0.3s ease;
        }

        .btn-primary:hover {
            background-color: var(--secondary-color);
            border-color: var(--secondary-color);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(59, 130, 246, 0.3);
        }

        .btn-secondary {
            background-color: #6b7280;
            border-color: #6b7280;
            padding: 0.75rem 2rem;
            font-weight: 500;
            border-radius: 10px;
        }

        .btn-outline-primary {
            color: var(--primary-color);
            border-color: var(--primary-color);
            padding: 0.75rem 2rem;
            font-weight: 500;
            border-radius: 10px;
        }

        .btn-outline-primary:hover {
            background-color: var(--primary-color);
            border-color: var(--primary-color);
        }

        /* File Upload */
        .file-upload-wrapper {
            position: relative;
            overflow: hidden;
            display: inline-block;
            width: 100%;
        }

        .file-upload-wrapper input[type=file] {
            position: absolute;
            left: -9999px;
        }

        .file-upload-label {
            display: block;
            padding: 2rem;
            background-color: #f9fafb;
            border: 2px dashed #d1d5db;
            border-radius: 10px;
            cursor: pointer;
            text-align: center;
            transition: all 0.3s ease;
        }

        .file-upload-label:hover {
            background-color: #f3f4f6;
            border-color: var(--secondary-color);
        }

        .file-upload-label i {
            font-size: 3rem;
            color: #9ca3af;
            margin-bottom: 0.75rem;
        }

        /* Progress Bar */
        .progress-container {
            margin-bottom: 2rem;
        }

        .progress {
            height: 8px;
            border-radius: 10px;
            background-color: #e5e7eb;
        }

        .progress-bar {
            background: linear-gradient(90deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            transition: width 0.3s ease;
        }

        /* Alert Styles */
        .alert-success {
            background-color: #d1fae5;
            border-color: #10b981;
            color: #065f46;
            border-radius: 10px;
        }

        .alert-danger {
            background-color: #fee2e2;
            border-color: #ef4444;
            color: #991b1b;
            border-radius: 10px;
        }

        /* Card Styles */
        .jurusan-card {
            border: 2px solid #e5e7eb;
            border-radius: 10px;
            padding: 1.5rem;
            margin-bottom: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .jurusan-card:hover {
            border-color: var(--secondary-color);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .jurusan-card.selected {
            border-color: var(--primary-color);
            background-color: #eff6ff;
        }

        /* Preview Modal */
        .preview-section {
            background-color: #f9fafb;
            border-radius: 10px;
            padding: 1.5rem;
            margin-bottom: 1rem;
        }

        .preview-label {
            font-weight: 600;
            color: var(--primary-color);
            margin-bottom: 0.25rem;
        }

        /* Loading Spinner */
        .loading-spinner {
            display: none;
            text-align: center;
            padding: 3rem;
        }

        .spinner-grow {
            width: 3rem;
            height: 3rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header-section {
                padding: 2rem 0;
            }
            
            .form-container {
                padding: 1.5rem;
                margin: -2rem 1rem 2rem;
            }
            
            .section-title {
                font-size: 1.1rem;
            }
        }

        /* Animations */
        .fade-in {
            animation: fadeIn 0.5s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Badge Styles */
        .badge-primary {
            background-color: var(--primary-color);
        }

        .badge-secondary {
            background-color: var(--secondary-color);
        }
    </style>
</head>
<body>
    <!-- Header Section -->
    <header class="header-section">
        <div class="container">
            <div class="row align-items-center">
                <div class="col-md-2 text-center">
                    <div class="school-logo mx-auto animate__animated animate__bounceIn">
                        <i class="bi bi-building" style="font-size: 3rem; color: var(--primary-color);"></i>
                    </div>
                </div>
                <div class="col-md-10 text-center text-md-start animate__animated animate__fadeInRight">
                    <h1 class="mb-2">SMKN 1 Purbalingga</h1>
                    <p class="mb-0 fs-5">Sistem Pendaftaran Siswa Baru Tahun Ajaran 2024/2025</p>
                    <small class="d-block mt-2 opacity-75">Jl. Jend. Sudirman No. 123, Purbalingga, Jawa Tengah</small>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="container">
        <div class="form-container animate__animated animate__fadeInUp">
            <!-- Progress Bar -->
            <div class="progress-container">
                <div class="d-flex justify-content-between mb-2">
                    <small class="text-muted">Progress Pengisian</small>
                    <small class="text-primary fw-bold" id="progressText">0%</small>
                </div>
                <div class="progress">
                    <div class="progress-bar" role="progressbar" style="width: 0%" id="progressBar"></div>
                </div>
            </div>

            <!-- Alert Messages -->
            <div class="alert alert-success d-none" id="successAlert" role="alert">
                <i class="bi bi-check-circle-fill me-2"></i>
                <span id="successMessage"></span>
            </div>

            <div class="alert alert-danger d-none" id="errorAlert" role="alert">
                <i class="bi bi-exclamation-triangle-fill me-2"></i>
                <span id="errorMessage"></span>
            </div>

            <!-- Registration Form -->
            <form id="registrationForm" novalidate>
                <!-- Section 1: Data Pribadi -->
                <div class="form-section fade-in">
                    <h3 class="section-title">
                        <i class="bi bi-person-fill"></i>Data Pribadi Siswa
                    </h3>
                    
                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <label for="fullName" class="form-label">Nama Lengkap <span class="text-danger">*</span></label>
                            <input type="text" class="form-control" id="fullName" name="fullName" required>
                            <div class="invalid-feedback">Nama lengkap harus diisi</div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <label for="nik" class="form-label">NIK <span class="text-danger">*</span></label>
                            <input type="text" class="form-control" id="nik" name="nik" pattern="[0-9]{16}" required>
                            <div class="invalid-feedback">NIK harus 16 digit angka</div>
                        </div>
                    </div>

                    <div class="row">
                        <div class="col-md-4 mb-3">
                            <label for="placeOfBirth" class="form-label">Tempat Lahir <span class="text-danger">*</span></label>
                            <input type="text" class="form-control" id="placeOfBirth" name="placeOfBirth" required>
                            <div class="invalid-feedback">Tempat lahir harus diisi</div>
                        </div>
                        
                        <div class="col-md-4 mb-3">
                            <label for="dateOfBirth" class="form-label">Tanggal Lahir <span class="text-danger">*</span></label>
                            <input type="date" class="form-control" id="dateOfBirth" name="dateOfBirth" required>
                            <div class="invalid-feedback">Tanggal lahir harus diisi</div>
                        </div>
                        
                        <div class="col-md-4 mb-3">
                            <label for="gender" class="form-label">Jenis Kelamin <span class="text-danger">*</span></label>
                            <select class="form-select" id="gender" name="gender" required>
                                <option value="">Pilih Jenis Kelamin</option>
                                <option value="L">Laki-laki</option>
                                <option value="P">Perempuan</option>
                            </select>
                            <div class="invalid-feedback">Jenis kelamin harus dipilih</div>
                        </div>
                    </div>

                    <div class="row">
                        <div class="col-md-4 mb-3">
                            <label for="religion" class="form-label">Agama <span class="text-danger">*</span></label>
                            <select class="form-select" id="religion" name="religion" required>
                                <option value="">Pilih Agama</option>
                                <option value="Islam">Islam</option>
                                <option value="Kristen">Kristen</option>
                                <option value="Katolik">Katolik</option>
                                <option value="Hindu">Hindu</option>
                                <option value="Buddha">Buddha</option>
                                <option value="Konghucu">Konghucu</option>
                            </select>
                            <div class="invalid-feedback">Agama harus dipilih</div>
                        </div>
                        
                        <div class="col-md-4 mb-3">
                            <label for="bloodType" class="form-label">Golongan Darah</label>
                            <select class="form-select" id="bloodType" name="bloodType">
                                <option value="">Pilih Golongan Darah</option>
                                <option value="A">A</option>
                                <option value="B">B</option>
                                <option value="AB">AB</option>
                                <option value="O">O</option>
                            </select>
                        </div>
                        
                        <div class="col-md-4 mb-3">
                            <label for="height" class="form-label">Tinggi Badan (cm)</label>
                            <input type="number" class="form-control" id="height" name="height" min="100" max="250">
                        </div>
                    </div>
                </div>

                <!-- Section 2: Data Alamat -->
                <div class="form-section fade-in">
                    <h3 class="section-title">
                        <i class="bi bi-geo-alt-fill"></i>Data Alamat
                    </h3>
                    
                    <div class="mb-3">
                        <label for="address" class="form-label">Alamat Lengkap <span class="text-danger">*</span></label>
                        <textarea class="form-control" id="address" name="address" rows="3" required></textarea>
                        <div class="invalid-feedback">Alamat harus diisi</div>
                    </div>

                    <div class="row">
                        <div class="col-md-3 mb-3">
                            <label for="province" class="form-label">Provinsi <span class="text-danger">*</span></label>
                            <select class="form-select" id="province" name="province" required>
                                <option value="">Pilih Provinsi</option>
                                <option value="Jawa Tengah">Jawa Tengah</option>
                                <option value="DKI Jakarta">DKI Jakarta</option>
                                <option value="Jawa Barat">Jawa Barat</option>
                                <option value="Jawa Timur">Jawa Timur</option>
                                <option value="DI Yogyakarta">DI Yogyakarta</option>
                            </select>
                            <div class="invalid-feedback">Provinsi harus dipilih</div>
                        </div>
                        
                        <div class="col-md-3 mb-3">
                            <label for="city" class="form-label">Kabupaten/Kota <span class="text-danger">*</span></label>
                            <input type="text" class="form-control" id="city" name="city" required>
                            <div class="invalid-feedback">Kabupaten/Kota harus diisi</div>
                        </div>
                        
                        <div class="col-md-3 mb-3">
                            <label for="district" class="form-label">Kecamatan <span class="text-danger">*</span></label>
                            <input type="text" class="form-control" id="district" name="district" required>
                            <div class="invalid-feedback">Kecamatan harus diisi</div>
                        </div>
                        
                        <div class="col-md-3 mb-3">
                            <label for="postalCode" class="form-label">Kode Pos</label>
                            <input type="text" class="form-control" id="postalCode" name="postalCode" pattern="[0-9]{5}">
                        </div>
                    </div>

                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <label for="phoneNumber" class="form-label">Nomor Telepon <span class="text-danger">*</span></label>
                            <input type="tel" class="form-control" id="phoneNumber" name="phoneNumber" required>
                            <div class="invalid-feedback">Nomor telepon harus diisi</div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <label for="email" class="form-label">Email <span class="text-danger">*</span></label>
                            <input type="email" class="form-control" id="email" name="email" required>
                            <div class="invalid-feedback">Email harus valid</div>
                        </div>
                    </div>
                </div>

                <!-- Section 3: Data Orang Tua/Wali -->
                <div class="form-section fade-in">
                    <h3 class="section-title">
                        <i class="bi bi-people-fill"></i>Data Orang Tua/Wali
                    </h3>
                    
                    <h5 class="mb-3 text-primary">Data Ayah</h5>
                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <label for="fatherName" class="form-label">Nama Ayah <span class="text-danger">*</span></label>
                            <input type="text" class="form-control" id="fatherName" name="fatherName" required>
                            <div class="invalid-feedback">Nama ayah harus diisi</div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <label for="fatherJob" class="form-label">Pekerjaan Ayah <span class="text-danger">*</span></label>
                            <input type="text" class="form-control" id="fatherJob" name="fatherJob" required>
                            <div class="invalid-feedback">Pekerjaan ayah harus diisi</div>
                        </div>
                    </div>

                    <h5 class="mb-3 mt-4 text-primary">Data Ibu</h5>
                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <label for="motherName" class="form-label">Nama Ibu <span class="text-danger">*</span></label>
                            <input type="text" class="form-control" id="motherName" name="motherName" required>
                            <div class="invalid-feedback">Nama ibu harus diisi</div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <label for="motherJob" class="form-label">Pekerjaan Ibu <span class="text-danger">*</span></label>
                            <input type="text" class="form-control" id="motherJob" name="motherJob" required>
                            <div class="invalid-feedback">Pekerjaan ibu harus diisi</div>
                        </div>
                    </div>

                    <h5 class="mb-3 mt-4 text-primary">Data Wali (jika ada)</h5>
                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <label for="guardianName" class="form-label">Nama Wali</label>
                            <input type="text" class="form-control" id="guardianName" name="guardianName">
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <label for="guardianJob" class="form-label">Pekerjaan Wali</label>
                            <input type="text" class="form-control" id="guardianJob" name="guardianJob">
                        </div>
                    </div>

                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <label for="parentPhone" class="form-label">No. HP Orang Tua/Wali <span class="text-danger">*</span></label>
                            <input type="tel" class="form-control" id="parentPhone" name="parentPhone" required>
                            <div class="invalid-feedback">Nomor HP harus diisi</div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <label for="parentIncome" class="form-label">Penghasilan Orang Tua/Bulan</label>
                            <select class="form-select" id="parentIncome" name="parentIncome">
                                <option value="">Pilih Range Penghasilan</option>
                                <option value="<1jt">< Rp 1.000.000</option>
                                <option value="1-2jt">Rp 1.000.000 - Rp 2.000.000</option>
                                <option value="2-3jt">Rp 2.000.000 - Rp 3.000.000</option>
                                <option value="3-5jt">Rp 3.000.000 - Rp 5.000.000</option>
                                <option value=">5jt">> Rp 5.000.000</option>
                            </select>
                        </div>
                    </div>
                </div>

                <!-- Section 4: Data Pendidikan -->
                <div class="form-section fade-in">
                    <h3 class="section-title">
                        <i class="bi bi-mortarboard-fill"></i>Data Pendidikan Sebelumnya
                    </h3>
                    
                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <label for="previousSchool" class="form-label">Asal Sekolah <span class="text-danger">*</span></label>
                            <input type="text" class="form-control" id="previousSchool" name="previousSchool" required>
                            <div class="invalid-feedback">Asal sekolah harus diisi</div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <label for="schoolAddress" class="form-label">Alamat Sekolah</label>
                            <input type="text" class="form-control" id="schoolAddress" name="schoolAddress">
                        </div>
                    </div>

                    <div class="row">
                        <div class="col-md-4 mb-3">
                            <label for="graduationYear" class="form-label">Tahun Lulus <span class="text-danger">*</span></label>
                            <input type="number" class="form-control" id="graduationYear" name="graduationYear" min="2020" max="2024" required>
                            <div class="invalid-feedback">Tahun lulus harus diisi</div>
                        </div>
                        
                        <div class="col-md-4 mb-3">
                            <label for="certificateNumber" class="form-label">No. Ijazah/SKL <span class="text-danger">*</span></label>
                            <input type="text" class="form-control" id="certificateNumber" name="certificateNumber" required>
                            <div class="invalid-feedback">Nomor ijazah harus diisi</div>
                        </div>
                        
                        <div class="col-md-4 mb-3">
                            <label for="unNumber" class="form-label">No. UN (jika ada)</label>
                            <input type="text" class="form-control" id="unNumber" name="unNumber">
                        </div>
                    </div>

                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <label for="averageGrade" class="form-label">Nilai Rata-rata Raport <span class="text-danger">*</span></label>
                            <input type="number" class="form-control" id="averageGrade" name="averageGrade" min="0" max="100" step="0.01" required>
                            <div class="invalid-feedback">Nilai rata-rata harus diisi</div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <label for="achievements" class="form-label">Prestasi (pisahkan dengan koma)</label>
                            <input type="text" class="form-control" id="achievements" name="achievements" placeholder="Contoh: Juara 1 Olimpiade Matematika, Juara 2 Futsal">
                        </div>
                    </div>
                </div>

                <!-- Section 5: Pilihan Jurusan -->
                <div class="form-section fade-in">
                    <h3 class="section-title">
                        <i class="bi bi-book-fill"></i>Pilihan Jurusan
                    </h3>
                    
                    <p class="text-muted mb-4">Pilih 1 jurusan yang diminati:</p>
                    
                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <div class="jurusan-card" data-jurusan="RPL">
                                <h5 class="mb-2">Rekayasa Perangkat Lunak (RPL)</h5>
                                <p class="mb-0 text-muted">Mempelajari pengembangan software, aplikasi, dan sistem komputer</p>
                                <div class="mt-2">
                                    <span class="badge badge-primary">Kuota: 36</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <div class="jurusan-card" data-jurusan="TKJ">
                                <h5 class="mb-2">Teknik Komputer dan Jaringan (TKJ)</h5>
                                <p class="mb-0 text-muted">Mempelajari instalasi jaringan, server, dan troubleshooting</p>
                                <div class="mt-2">
                                    <span class="badge badge-primary">Kuota: 36</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <div class="jurusan-card" data-jurusan="MM">
                                <h5 class="mb-2">Multimedia (MM)</h5>
                                <p class="mb-0 text-muted">Mempelajari desain grafis, animasi, dan produksi video</p>
                                <div class="mt-2">
                                    <span class="badge badge-primary">Kuota: 36</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <div class="jurusan-card" data-jurusan="AK">
                                <h5 class="mb-2">Akuntansi (AK)</h5>
                                <p class="mb-0 text-muted">Mempelajari pencatatan keuangan dan perpajakan</p>
                                <div class="mt-2">
                                    <span class="badge badge-primary">Kuota: 36</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <div class="jurusan-card" data-jurusan="OTKP">
                                <h5 class="mb-2">Otomatisasi dan Tata Kelola Perkantoran (OTKP)</h5>
                                <p class="mb-0 text-muted">Mempelajari administrasi perkantoran dan manajemen</p>
                                <div class="mt-2">
                                    <span class="badge badge-primary">Kuota: 36</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <div class="jurusan-card" data-jurusan="BDP">
                                <h5 class="mb-2">Bisnis Daring dan Pemasaran (BDP)</h5>
                                <p class="mb-0 text-muted">Mempelajari digital marketing dan e-commerce</p>
                                <div class="mt-2">
                                    <span class="badge badge-primary">Kuota: 36</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <input type="hidden" id="selectedJurusan" name="selectedJurusan" required>
                    <div class="invalid-feedback" id="jurusanFeedback">Pilih salah satu jurusan</div>
                </div>

                <!-- Section 6: Upload Dokumen -->
                <div class="form-section fade-in">
                    <h3 class="section-title">
                        <i class="bi bi-file-earmark-fill"></i>Upload Dokumen
                    </h3>
                    
                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <label class="form-label">Pas Foto <span class="text-danger">*</span></label>
                            <div class="file-upload-wrapper">
                                <input type="file" class="form-control" id="photo" name="photo" accept="image/*" required>
                                <label for="photo" class="file-upload-label">
                                    <i class="bi bi-camera-fill"></i>
                                    <p class="mb-0">Klik untuk upload pas foto</p>
                                    <small class="text-muted">Format: JPG/PNG, Max: 2MB</small>
                                </label>
                            </div>
                            <div class="invalid-feedback">Pas foto harus diupload</div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <label class="form-label">Scan Kartu Keluarga <span class="text-danger">*</span></label>
                            <div class="file-upload-wrapper">
                                <input type="file" class="form-control" id="kk" name="kk" accept="image/*,.pdf" required>
                                <label for="kk" class="file-upload-label">
                                    <i class="bi bi-file-earmark-text-fill"></i>
                                    <p class="mb-0">Klik untuk upload KK</p>
                                    <small class="text-muted">Format: JPG/PNG/PDF, Max: 5MB</small>
                                </label>
                            </div>
                            <div class="invalid-feedback">KK harus diupload</div>
                        </div>
                    </div>

                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <label class="form-label">Scan Akta Kelahiran <span class="text-danger">*</span></label>
                            <div class="file-upload-wrapper">
                                <input type="file" class="form-control" id="akta" name="akta" accept="image/*,.pdf" required>
                                <label for="akta" class="file-upload-label">
                                    <i class="bi bi-file-earmark-text-fill"></i>
                                    <p class="mb-0">Klik untuk upload akta</p>
                                    <small class="text-muted">Format: JPG/PNG/PDF, Max: 5MB</small>
                                </label>
                            </div>
                            <div class="invalid-feedback">Akta kelahiran harus diupload</div>
                        </div>
                        
                        <div class="col-md-6 mb-3">
                            <label class="form-label">Scan Ijazah/SKL <span class="text-danger">*</span></label>
                            <div class="file-upload-wrapper">
                                <input type="file" class="form-control" id="ijazah" name="ijazah" accept="image/*,.pdf" required>
                                <label for="ijazah" class="file-upload-label">
                                    <i class="bi bi-file-earmark-text-fill"></i>
                                    <p class="mb-0">Klik untuk upload ijazah</p>
                                    <small class="text-muted">Format: JPG/PNG/PDF, Max: 5MB</small>
                                </label>
                            </div>
                            <div class="invalid-feedback">Ijazah/SKL harus diupload</div>
                        </div>
                    </div>
                </div>

                <!-- Section 7: Pernyataan -->
                <div class="form-section fade-in">
                    <h3 class="section-title">
                        <i class="bi bi-check-circle-fill"></i>Pernyataan
                    </h3>
                    
                    <div class="form-check mb-3">
                        <input class="form-check-input" type="checkbox" id="statement1" name="statement1" required>
                        <label class="form-check-label" for="statement1">
                            Saya menyatakan bahwa data yang diisi adalah benar dan dapat dipertanggungjawabkan
                        </label>
                        <div class="invalid-feedback">Anda harus menyetujui pernyataan ini</div>
                    </div>
                    
                    <div class="form-check mb-3">
                        <input class="form-check-input" type="checkbox" id="statement2" name="statement2" required>
                        <label class="form-check-label" for="statement2">
                            Saya bersedia mengikuti semua seleksi dan peraturan yang berlaku di SMKN 1 Purbalingga
                        </label>
                        <div class="invalid-feedback">Anda harus menyetujui pernyataan ini</div>
                    </div>
                    
                    <div class="form-check">
                        <input class="form-check-input" type="checkbox" id="statement3" name="statement3" required>
                        <label class="form-check-label" for="statement3">
                            Saya menyetujui data saya digunakan untuk keperluan administrasi sekolah
                        </label>
                        <div class="invalid-feedback">Anda harus menyetujui pernyataan ini</div>
                    </div>
                </div>

                <!-- Action Buttons -->
                <div class="d-flex justify-content-between mt-4">
                    <button type="button" class="btn btn-outline-primary" onclick="resetForm()">
                        <i class="bi bi-arrow-counterclockwise me-2"></i>Reset Form
                    </button>
                    <div>
                        <button type="button" class="btn btn-secondary me-2" onclick="previewData()">
                            <i class="bi bi-eye me-2"></i>Preview Data
                        </button>
                        <button type="submit" class="btn btn-primary">
                            <i class="bi bi-send-fill me-2"></i>Kirim Pendaftaran
                        </button>
                    </div>
                </div>
            </form>

            <!-- Loading Spinner -->
            <div class="loading-spinner" id="loadingSpinner">
                <div class="spinner-grow text-primary" role="status">
                    <span class="visually-hidden">Loading...</span>
                </div>
                <p class="mt-3 text-muted">Sedang memproses data...</p>
            </div>
        </div>
    </main>

    <!-- Preview Modal -->
    <div class="modal fade" id="previewModal" tabindex="-1">
        <div class="modal-dialog modal-lg modal-dialog-scrollable">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">Preview Data Pendaftaran</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
                </div>
                <div class="modal-body" id="previewContent">
                    <!-- Preview content will be inserted here -->
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Tutup</button>
                    <button type="button" class="btn btn-primary" onclick="submitForm()">Kirim Pendaftaran</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    
    <script>
        // Initialize variables
        let selectedJurusan = '';
        let formProgress = 0;

        // Update progress bar
        function updateProgress() {
            const form = document.getElementById('registrationForm');
            const inputs = form.querySelectorAll('input[required], select[required], textarea[required]');
            const filledInputs = Array.from(inputs).filter(input => {
                if (input.type === 'checkbox') {
                    return input.checked;
                }
                return input.value.trim() !== '';
            });
            
            formProgress = Math.round((filledInputs.length / inputs.length) * 100);
            document.getElementById('progressBar').style.width = formProgress + '%';
            document.getElementById('progressText').textContent = formProgress + '%';
        }

        // Jurusan selection
        document.querySelectorAll('.jurusan-card').forEach(card => {
            card.addEventListener('click', function() {
                document.querySelectorAll('.jurusan-card').forEach(c => c.classList.remove('selected'));
                this.classList.add('selected');
                selectedJurusan = this.dataset.jurusan;
                document.getElementById('selectedJurusan').value = selectedJurusan;
                updateProgress();
            });
        });

        // File upload preview
        document.querySelectorAll('input[type="file"]').forEach(input => {
            input.addEventListener('change', function() {
                const label = this.nextElementSibling;
                const fileName = this.files[0]?.name || 'Klik untuk upload';
                label.querySelector('p').textContent = fileName;
                updateProgress();
            });
        });

        // Form validation
        document.getElementById('registrationForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            if (!validateForm()) {
                return;
            }
            
            showLoading();
            
            // Simulate form submission
            setTimeout(() => {
                hideLoading();
                showSuccess();
                this.reset();
                selectedJurusan = '';
                document.querySelectorAll('.jurusan-card').forEach(c => c.classList.remove('selected'));
                updateProgress();
            }, 2000);
        });

        function validateForm() {
            const form = document.getElementById('registrationForm');
            let isValid = true;
            
            // Check required fields
            form.querySelectorAll('[required]').forEach(field => {
                if (!field.value.trim() && field.type !== 'checkbox') {
                    field.classList.add('is-invalid');
                    isValid = false;
                } else if (field.type === 'checkbox' && !field.checked) {
                    field.classList.add('is-invalid');
                    isValid = false;
                } else {
                    field.classList.remove('is-invalid');
                }
            });
            
            // Check jurusan selection
            if (!selectedJurusan) {
                document.getElementById('jurusanFeedback').style.display = 'block';
                isValid = false;
            } else {
                document.getElementById('jurusanFeedback').style.display = 'none';
            }
            
            // Check file uploads
            const requiredFiles = ['photo', 'kk', 'akta', 'ijazah'];
            requiredFiles.forEach(fileId => {
                const fileInput = document.getElementById(fileId);
                if (!fileInput.files.length) {
                    fileInput.classList.add('is-invalid');
                    isValid = false;
                } else {
                    fileInput.classList.remove('is-invalid');
                }
            });
            
            if (!isValid) {
                showError('Mohon lengkapi semua field yang wajib diisi!');
            }
            
            return isValid;
        }

        function previewData() {
            if (!validateForm()) {
                return;
            }
            
            const form = document.getElementById('registrationForm');
            const formData = new FormData(form);
            let previewHTML = '';
            
            // Data Pribadi
            previewHTML += `
                <div class="preview-section">
                    <h5 class="mb-3"><i class="bi bi-person-fill me-2"></i>Data Pribadi</h5>
                    <div class="row">
                        <div class="col-md-6">
                            <p><span class="preview-label">Nama Lengkap:</span> ${formData.get('fullName')}</p>
                            <p><span class="preview-label">NIK:</span> ${formData.get('nik')}</p>
                            <p><span class="preview-label">Tempat, Tanggal Lahir:</span> ${formData.get('placeOfBirth')}, ${formData.get('dateOfBirth')}</p>
                            <p><span class="preview-label">Jenis Kelamin:</span> ${formData.get('gender') === 'L' ? 'Laki-laki' : 'Perempuan'}</p>
                        </div>
                        <div class="col-md-6">
                            <p><span class="preview-label">Agama:</span> ${formData.get('religion')}</p>
                            <p><span class="preview-label">Golongan Darah:</span> ${formData.get('bloodType') || '-'}</p>
                            <p><span class="preview-label">Tinggi Badan:</span> ${formData.get('height') || '-'} cm</p>
                        </div>
                    </div>
                </div>
            `;
            
            // Data Alamat
            previewHTML += `
                <div class="preview-section">
                    <h5 class="mb-3"><i class="bi bi-geo-alt-fill me-2"></i>Data Alamat</h5>
                    <p><span class="preview-label">Alamat:</span> ${formData.get('address')}</p>
                    <div class="row">
                        <div class="col-md-6">
                            <p><span class="preview-label">Provinsi:</span> ${formData.get('province')}</p>
                            <p><span class="preview-label">Kabupaten/Kota:</span> ${formData.get('city')}</p>
                        </div>
                        <div class="col-md-6">
                            <p><span class="preview-label">Kecamatan:</span> ${formData.get('district')}</p>
                            <p><span class="preview-label">Kode Pos:</span> ${formData.get('postalCode') || '-'}</p>
                        </div>
                    </div>
                    <p><span class="preview-label">No. Telepon:</span> ${formData.get('phoneNumber')}</p>
                    <p><span class="preview-label">Email:</span> ${formData.get('email')}</p>
                </div>
            `;
            
            // Data Orang Tua
            previewHTML += `
                <div class="preview-section">
                    <h5 class="mb-3"><i class="bi bi-people-fill me-2"></i>Data Orang Tua/Wali</h5>
                    <div class="row">
                        <div class="col-md-6">
                            <h6 class="text-primary">Ayah</h6>
                            <p><span class="preview-label">Nama:</span> ${formData.get('fatherName')}</p>
                            <p><span class="preview-label">Pekerjaan:</span> ${formData.get('fatherJob')}</p>
                        </div>
                        <div class="col-md-6">
                            <h6 class="text-primary">Ibu</h6>
                            <p><span class="preview-label">Nama:</span> ${formData.get('motherName')}</p>
                            <p><span class="preview-label">Pekerjaan:</span> ${formData.get('motherJob')}</p>
                        </div>
                    </div>
                    ${formData.get('guardianName') ? `
                    <div class="row mt-3">
                        <div class="col-md-6">
                            <h6 class="text-primary">Wali</h6>
                            <p><span class="preview-label">Nama:</span> ${formData.get('guardianName')}</p>
                            <p><span class="preview-label">Pekerjaan:</span> ${formData.get('guardianJob')}</p>
                        </div>
                    </div>
                    ` : ''}
                    <p><span class="preview-label">No. HP Orang Tua/Wali:</span> ${formData.get('parentPhone')}</p>
                    <p><span class="preview-label">Penghasilan:</span> ${formData.get('parentIncome') || '-'}</p>
                </div>
            `;
            
            // Data Pendidikan
            previewHTML += `
                <div class="preview-section">
                    <h5 class="mb-3"><i class="bi bi-mortarboard-fill me-2"></i>Data Pendidikan</h5>
                    <p><span class="preview-label">Asal Sekolah:</span> ${formData.get('previousSchool')}</p>
                    <p><span class="preview-label">Alamat Sekolah:</span> ${formData.get('schoolAddress') || '-'}</p>
                    <div class="row">
                        <div class="col-md-4">
                            <p><span class="preview-label">Tahun Lulus:</span> ${formData.get('graduationYear')}</p>
                        </div>
                        <div class="col-md-4">
                            <p><span class="preview-label">No. Ijazah/SKL:</span> ${formData.get('certificateNumber')}</p>
                        </div>
                        <div class="col-md-4">
                            <p><span class="preview-label">No. UN:</span> ${formData.get('unNumber') || '-'}</p>
                        </div>
                    </div>
                    <p><span class="preview-label">Nilai Rata-rata:</span> ${formData.get('averageGrade')}</p>
                    <p><span class="preview-label">Prestasi:</span> ${formData.get('achievements') || '-'}</p>
                </div>
            `;
            
            // Pilihan Jurusan
            const jurusanNames = {
                'RPL': 'Rekayasa Perangkat Lunak (RPL)',
                'TKJ': 'Teknik Komputer dan Jaringan (TKJ)',
                'MM': 'Multimedia (MM)',
                'AK': 'Akuntansi (AK)',
                'OTKP': 'Otomatisasi dan Tata Kelola Perkantoran (OTKP)',
                'BDP': 'Bisnis Daring dan Pemasaran (BDP)'
            };
            
            previewHTML += `
                <div class="preview-section">
                    <h5 class="mb-3"><i class="bi bi-book-fill me-2"></i>Pilihan Jurusan</h5>
                    <p><span class="preview-label">Jurusan Dipilih:</span> ${jurusanNames[selectedJurusan]}</p>
                </div>
            `;
            
            // Dokumen
            previewHTML += `
                <div class="preview-section">
                    <h5 class="mb-3"><i class="bi bi-file-earmark-fill me-2"></i>Dokumen Terupload</h5>
                    <ul class="list-unstyled">
                        <li><i class="bi bi-check-circle-fill text-success me-2"></i>Pas Foto</li>
                        <li><i class="bi bi-check-circle-fill text-success me-2"></i>Kartu Keluarga</li>
                        <li><i class="bi bi-check-circle-fill text-success me-2"></i>Akta Kelahiran</li>
                        <li><i class="bi bi-check-circle-fill text-success me-2"></i>Ijazah/SKL</li>
                    </ul>
                </div>
            `;
            
            document.getElementById('previewContent').innerHTML = previewHTML;
            new bootstrap.Modal(document.getElementById('previewModal')).show();
        }

        function submitForm() {
            bootstrap.Modal.getInstance(document.getElementById('previewModal')).hide();
            document.getElementById('registrationForm').dispatchEvent(new Event('submit'));
        }

        function resetForm() {
            if (confirm('Apakah Anda yakin ingin mereset semua data yang telah diisi?')) {
                document.getElementById('registrationForm').reset();
                selectedJurusan = '';
                document.querySelectorAll('.jurusan-card').forEach(c => c.classList.remove('selected'));
                document.querySelectorAll('.is-invalid').forEach(el => el.classList.remove('is-invalid'));
                document.querySelectorAll('.file-upload-label p').forEach(el => {
                    if (el.parentElement.parentElement.querySelector('input[type="file"]')) {
                        el.textContent = 'Klik untuk upload';
                    }
                });
                updateProgress();
                hideAlerts();
            }
        }

        function showLoading() {
            document.getElementById('loadingSpinner').style.display = 'block';
            document.getElementById('registrationForm').style.display = 'none';
        }

        function hideLoading() {
            document.getElementById('loadingSpinner').style.display = 'none';
            document.getElementById('registrationForm').style.display = 'block';
        }

        function showSuccess() {
            const regNumber = 'REG-' + Date.now().toString().slice(-8);
            document.getElementById('successMessage').textContent = 
                `Pendaftaran berhasil! Nomor pendaftaran Anda: ${regNumber}. Silakan catat nomor ini untuk verifikasi selanjutnya.`;
            document.getElementById('successAlert').classList.remove('d-none');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function showError(message) {
            document.getElementById('errorMessage').textContent = message;
            document.getElementById('errorAlert').classList.remove('d-none');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function hideAlerts() {
            document.getElementById('successAlert').classList.add('d-none');
            document.getElementById('errorAlert').classList.add('d-none');
        }

        // Add input event listeners for progress tracking
        document.querySelectorAll('input, select, textarea').forEach(input => {
            input.addEventListener('input', updateProgress);
            input.addEventListener('change', updateProgress);
        });

        // Initialize progress on page load
        updateProgress();
    </script>
</body>
</html>
