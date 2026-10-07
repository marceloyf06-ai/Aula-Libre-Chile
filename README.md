<!DOCTYPE html>
<html lang="es" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aula Virtual - Exámenes Libres Chile (1° Básico a 4° Medio)</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            50: '#eef2ff',
                            100: '#e0e7ff',
                            500: '#6366f1',
                            600: '#4f46e5',
                            700: '#4338ca',
                            900: '#312e81',
                        }
                    }
                }
            }
        }
    </script>
    <!-- FontAwesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; }
        .fade-in { animation: fadeIn 0.3s ease-in-out forwards; }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(6px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body class="h-full bg-slate-50 text-slate-800 flex flex-col">

    <!-- Top Navigation Bar -->
    <header class="bg-indigo-900 text-white shadow-md sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16 items-center">
                <div class="flex items-center space-x-3 cursor-pointer" onclick="switchTab('home')">
                    <div class="bg-indigo-600 p-2 rounded-xl text-white shadow-inner flex items-center justify-center">
                        <i class="fa-solid fa-graduation-cap text-xl"></i>
                    </div>
                    <div>
                        <span class="font-bold text-lg tracking-tight block leading-tight">AulaLibre<span class="text-indigo-400">.cl</span></span>
                        <span class="text-xs text-indigo-200 font-medium">Validación de Estudios 1°B a 4°M</span>
                    </div>
                </div>
                <!-- Desktop Nav -->
                <nav class="hidden md:flex space-x-1 lg:space-x-3 items-center">
                    <button onclick="switchTab('home')" id="nav-home" class="nav-btn px-3 py-2 rounded-lg text-sm font-medium transition bg-indigo-800 text-white"><i class="fa-solid fa-home mr-1.5"></i> Inicio</button>
                    <button onclick="switchTab('courses')" id="nav-courses" class="nav-btn px-3 py-2 rounded-lg text-sm font-medium transition text-indigo-200 hover:bg-indigo-800 hover:text-white"><i class="fa-solid fa-book-open mr-1.5"></i> 12 Cursos & OA</button>
                    <button onclick="switchTab('progress')" id="nav-progress" class="nav-btn px-3 py-2 rounded-lg text-sm font-medium transition text-indigo-200 hover:bg-indigo-800 hover:text-white"><i class="fa-solid fa-chart-line mr-1.5"></i> Mi Progreso</button>
                    <button onclick="switchTab('admin')" id="nav-admin" class="nav-btn px-3 py-2 rounded-lg text-sm font-medium transition text-indigo-200 hover:bg-indigo-800 hover:text-white border border-indigo-700"><i class="fa-solid fa-gear mr-1.5"></i> Panel Admin & Drive</button>
                </nav>
                <!-- User badge / Mobile menu toggle -->
                <div class="flex items-center space-x-3">
                    <div class="hidden sm:flex items-center space-x-2 bg-indigo-800/60 px-3 py-1.5 rounded-full border border-indigo-700/50">
                        <img src="https://placehold.co/32x32/6366f1/ffffff?text=AL" alt="Avatar" class="w-7 h-7 rounded-full">
                        <span class="text-xs font-medium text-indigo-100">Estudiante Pro</span>
                    </div>
                    <button onclick="toggleMobileMenu()" class="md:hidden p-2 rounded-lg text-indigo-200 hover:text-white hover:bg-indigo-800 focus:outline-none">
                        <i class="fa-solid fa-bars text-xl"></i>
                    </button>
                </div>
            </div>
        </div>
        <!-- Mobile menu dropdown -->
        <div id="mobile-menu" class="hidden md:hidden bg-indigo-950 px-4 pt-2 pb-4 space-y-1 border-t border-indigo-800">
            <button onclick="switchTab('home'); toggleMobileMenu();" class="block w-full text-left px-3 py-2 rounded-md text-base font-medium text-white hover:bg-indigo-900"><i class="fa-solid fa-home mr-2"></i> Inicio</button>
            <button onclick="switchTab('courses'); toggleMobileMenu();" class="block w-full text-left px-3 py-2 rounded-md text-base font-medium text-indigo-200 hover:bg-indigo-900 hover:text-white"><i class="fa-solid fa-book-open mr-2"></i> 12 Cursos & OA</button>
            <button onclick="switchTab('progress'); toggleMobileMenu();" class="block w-full text-left px-3 py-2 rounded-md text-base font-medium text-indigo-200 hover:bg-indigo-900 hover:text-white"><i class="fa-solid fa-chart-line mr-2"></i> Mi Progreso</button>
            <button onclick="switchTab('admin'); toggleMobileMenu();" class="block w-full text-left px-3 py-2 rounded-md text-base font-medium text-indigo-200 hover:bg-indigo-900 hover:text-white"><i class="fa-solid fa-gear mr-2"></i> Panel Admin & Drive</button>
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-6">

        <!-- TAB 1: HOME -->
        <section id="tab-home" class="tab-content fade-in space-y-6">
            <!-- Hero Banner -->
            <div class="relative overflow-hidden bg-gradient-to-r from-indigo-700 via-indigo-600 to-purple-700 rounded-2xl shadow-xl text-white p-6 sm:p-10">
                <div class="relative z-10 max-w-2xl">
                    <span class="inline-block bg-indigo-500/30 text-indigo-100 text-xs font-semibold px-3 py-1 rounded-full uppercase tracking-wider mb-4 border border-indigo-400/30">
                        <i class="fa-solid fa-shield-check mr-1"></i> MINEDUC Exámenes Libres 2026 • 12 Niveles
                    </span>
                    <h1 class="text-3xl sm:text-4xl font-extrabold tracking-tight mb-3">
                        Prepara tu Validación de Estudios desde 1° Básico a 4° Medio
                    </h1>
                    <p class="text-indigo-100 text-base sm:text-lg mb-6 leading-relaxed">
                        Accede a guías de estudio sincronizadas con Google Drive, Objetivos de Aprendizaje (OA) oficiales y ensayos interactivos para todos los cursos.
                    </p>
                    <div class="flex flex-wrap gap-3">
                        <button onclick="switchTab('courses')" class="bg-white text-indigo-700 hover:bg-indigo-50 font-semibold px-6 py-3 rounded-xl shadow transition flex items-center">
                            <i class="fa-solid fa-rocket mr-2"></i> Ver los 12 Cursos
                        </button>
                        <button onclick="switchTab('admin')" class="bg-indigo-800/80 hover:bg-indigo-800 text-white font-medium px-5 py-3 rounded-xl border border-indigo-500/40 transition flex items-center">
                            <i class="fa-brands fa-google-drive mr-2"></i> Configurar Enlaces Drive
                        </button>
                    </div>
                </div>
                <div class="absolute right-[-20px] bottom-[-30px] opacity-10 pointer-events-none text-9xl">
                    <i class="fa-solid fa-graduation-cap"></i>
                </div>
            </div>

            <!-- Stats / Highlights -->
            <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
                <div class="bg-white p-5 rounded-xl shadow-sm border border-slate-100 flex items-center space-x-4">
                    <div class="bg-indigo-50 text-indigo-600 p-3 rounded-xl"><i class="fa-solid fa-graduation-cap text-xl"></i></div>
                    <div>
                        <div class="text-2xl font-bold text-slate-800">12</div>
                        <div class="text-xs text-slate-500">Cursos (1°B a 4°M)</div>
                    </div>
                </div>
                <div class="bg-white p-5 rounded-xl shadow-sm border border-slate-100 flex items-center space-x-4">
                    <div class="bg-emerald-50 text-emerald-600 p-3 rounded-xl"><i class="fa-solid fa-book text-xl"></i></div>
                    <div>
                        <div class="text-2xl font-bold text-slate-800">60+</div>
                        <div class="text-xs text-slate-500">Asignaturas Oficiales</div>
                    </div>
                </div>
                <div class="bg-white p-5 rounded-xl shadow-sm border border-slate-100 flex items-center space-x-4">
                    <div class="bg-blue-50 text-blue-600 p-3 rounded-xl"><i class="fa-brands fa-google-drive text-xl"></i></div>
                    <div>
                        <div class="text-2xl font-bold text-slate-800">Cloud</div>
                        <div class="text-xs text-slate-500">Sincronizado con Drive</div>
                    </div>
                </div>
                <div class="bg-white p-5 rounded-xl shadow-sm border border-slate-100 flex items-center space-x-4">
                    <div class="bg-purple-50 text-purple-600 p-3 rounded-xl"><i class="fa-solid fa-square-poll-vertical text-xl"></i></div>
                    <div>
                        <div class="text-2xl font-bold text-slate-800">100%</div>
                        <div class="text-xs text-slate-500">Ensayos Interactivos</div>
                    </div>
                </div>
            </div>

            <!-- Quick Level Selector Grid (All 12 Courses) -->
            <div class="space-y-4">
                <div class="flex justify-between items-center">
                    <h2 class="text-xl font-bold text-slate-900"><i class="fa-solid fa-layer-group text-indigo-600 mr-2"></i> Selecciona tu Curso (1° Básico a 4° Medio)</h2>
                    <button onclick="switchTab('courses')" class="text-sm font-semibold text-indigo-600 hover:text-indigo-800">Ver panel completo &rarr;</button>
                </div>
                <div id="home-courses-grid" class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-4">
                    <!-- Populated via JS -->
                </div>
            </div>
        </section>

        <!-- TAB 2: COURSES & ASIGNATURAS & OA -->
        <section id="tab-courses" class="tab-content hidden fade-in space-y-6">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 bg-white p-6 rounded-2xl shadow-sm border border-slate-200">
                <div>
                    <h2 class="text-2xl font-bold text-slate-900">Catálogo Completo: 12 Cursos & Asignaturas</h2>
                    <p class="text-slate-500 text-sm mt-1">Elige tu nivel educativo y revisa las 5 a 6 asignaturas oficiales con guías en Google Drive.</p>
                </div>
                <div class="flex items-center space-x-3">
                    <label for="grade-select" class="text-xs font-bold text-slate-700 uppercase tracking-wide">Nivel:</label>
                    <select id="grade-select" onchange="onGradeChange(this.value)" class="bg-slate-50 border border-slate-300 text-slate-800 text-sm rounded-xl px-3 py-2.5 focus:ring-2 focus:ring-indigo-500 focus:outline-none font-medium">
                        <!-- Populated via JS -->
                    </select>
                </div>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-4 gap-6">
                <!-- Left Sidebar: Subjects -->
                <div class="lg:col-span-1 space-y-3">
                    <h3 class="text-xs font-bold text-slate-400 uppercase tracking-wider px-1">Asignaturas (5 a 6 por curso)</h3>
                    <div id="subjects-list" class="space-y-2"></div>

                    <!-- Upgrade Box -->
                    <div class="bg-gradient-to-br from-indigo-900 to-indigo-800 text-white p-4 rounded-xl shadow-md mt-6">
                        <div class="flex items-center space-x-2 text-indigo-300 mb-2">
                            <i class="fa-solid fa-crown text-amber-400"></i>
                            <span class="text-xs font-bold uppercase tracking-wider">Acceso Premium</span>
                        </div>
                        <h4 class="font-bold text-sm mb-1">Desbloquea todos los PDF de Drive</h4>
                        <p class="text-xs text-indigo-200 mb-3 leading-relaxed">Acceso a carpetas compartidas sin restricciones para exámenes libres.</p>
                        <button onclick="openCheckoutModal()" class="w-full bg-amber-400 hover:bg-amber-300 text-slate-900 font-bold text-xs py-2.5 rounded-lg transition shadow">
                            Obtener Pase Anual ($29.990)
                        </button>
                    </div>
                </div>

                <!-- Right Content Area -->
                <div class="lg:col-span-3 space-y-6">
                    <div id="subject-detail-view" class="bg-white rounded-2xl shadow-sm border border-slate-200 p-6">
                        <!-- Populated via JS -->
                    </div>
                </div>
            </div>
        </section>

        <!-- TAB 3: MI PROGRESO -->
        <section id="tab-progress" class="tab-content hidden fade-in space-y-6">
            <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200 flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
                <div>
                    <h2 class="text-2xl font-bold text-slate-900">Seguimiento de Progreso</h2>
                    <p class="text-slate-500 text-sm mt-1">Revisa tus unidades completadas y puntajes en evaluaciones de práctica.</p>
                </div>
                <div class="bg-indigo-50 border border-indigo-100 px-4 py-2.5 rounded-xl flex items-center space-x-3">
                    <div class="text-indigo-600 text-xl font-bold">70%</div>
                    <div>
                        <div class="text-xs font-bold text-indigo-900 uppercase">Avance General</div>
                        <div class="text-[11px] text-indigo-600">Preparación Exámenes MINEDUC</div>
                    </div>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-xs font-bold uppercase text-slate-400">Guías Descargadas</span>
                        <i class="fa-solid fa-file-arrow-down text-indigo-600 bg-indigo-50 p-2.5 rounded-lg"></i>
                    </div>
                    <div class="text-3xl font-extrabold text-slate-800 mb-1">18 / 30</div>
                    <div class="w-full bg-slate-100 h-2 rounded-full overflow-hidden mb-2">
                        <div class="bg-indigo-600 h-full rounded-full" style="width: 60%"></div>
                    </div>
                    <span class="text-xs text-slate-500">Sincronizado con Google Drive</span>
                </div>
                <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-xs font-bold uppercase text-slate-400">Tests Realizados</span>
                        <i class="fa-solid fa-square-check text-emerald-600 bg-emerald-50 p-2.5 rounded-lg"></i>
                    </div>
                    <div class="text-3xl font-extrabold text-slate-800 mb-1">12 Pruebas</div>
                    <div class="w-full bg-slate-100 h-2 rounded-full overflow-hidden mb-2">
                        <div class="bg-emerald-500 h-full rounded-full" style="width: 85%"></div>
                    </div>
                    <span class="text-xs text-slate-500">Promedio de logro: 88%</span>
                </div>
                <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-xs font-bold uppercase text-slate-400">Membresía</span>
                        <i class="fa-solid fa-crown text-amber-500 bg-amber-50 p-2.5 rounded-lg"></i>
                    </div>
                    <div class="text-xl font-bold text-slate-800 mb-1">Pase Pro Activo</div>
                    <div class="text-xs text-slate-500 mb-3">Acceso a los 12 Cursos</div>
                    <span class="inline-block bg-emerald-100 text-emerald-800 font-semibold text-[11px] px-2.5 py-0.5 rounded-full">Verificado</span>
                </div>
            </div>
        </section>

        <!-- TAB 4: ADMIN PANEL & DRIVE CONFIG -->
        <section id="tab-admin" class="tab-content hidden fade-in space-y-6">
            <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200">
                <div class="flex items-center justify-between mb-4">
                    <div>
                        <h2 class="text-2xl font-bold text-slate-900"><i class="fa-brands fa-google-drive text-indigo-600 mr-2"></i> Panel Admin & Conexión con Google Drive</h2>
                        <p class="text-slate-500 text-sm mt-1">Configura los enlaces compartidos de tus carpetas o archivos de Google Drive para que se enlacen automáticamente en cada guía.</p>
                    </div>
                    <span class="bg-indigo-100 text-indigo-800 text-xs font-bold px-3 py-1 rounded-lg">Netlify Ready</span>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <!-- Google Drive Link Configuration Form -->
                <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200 space-y-4">
                    <h3 class="font-bold text-lg text-slate-800 flex items-center">
                        <i class="fa-solid fa-link text-indigo-600 mr-2"></i> Vincular Enlace de Google Drive
                    </h3>
                    <form id="admin-drive-form" onsubmit="handleDriveLinkSubmit(event)" class="space-y-4">
                        <div>
                            <label class="block text-xs font-bold text-slate-700 uppercase mb-1">Seleccionar Curso</label>
                            <select id="drive-course-target" class="w-full bg-slate-50 border border-slate-300 rounded-xl px-3 py-2.5 text-sm font-medium focus:ring-2 focus:ring-indigo-500 focus:outline-none">
                                <!-- Populated dynamically -->
                            </select>
                        </div>
                        <div>
                            <label class="block text-xs font-bold text-slate-700 uppercase mb-1">Nombre de la Guía o Material</label>
                            <input type="text" id="drive-guide-title" required placeholder="Ej. Guía Oficial Unidad 1 - Matemáticas" class="w-full bg-slate-50 border border-slate-300 rounded-xl px-3 py-2.5 text-sm focus:ring-2 focus:ring-indigo-500 focus:outline-none">
                        </div>
                        <div>
                            <label class="block text-xs font-bold text-slate-700 uppercase mb-1">Enlace Compartido de Google Drive (URL)</label>
                            <input type="url" id="drive-url-input" required placeholder="https://drive.google.com/file/d/..." class="w-full bg-slate-50 border border-slate-300 rounded-xl px-3 py-2.5 text-sm focus:ring-2 focus:ring-indigo-500 focus:outline-none">
                        </div>
                        <button type="submit" class="w-full bg-indigo-600 hover:bg-indigo-700 text-white font-semibold py-3 rounded-xl transition shadow flex items-center justify-center">
                            <i class="fa-solid fa-cloud-arrow-up mr-2"></i> Guardar Enlace Drive
                        </button>
                    </form>
                </div>

                <!-- Status & Connected Drive Links -->
                <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200 space-y-4">
                    <h3 class="font-bold text-lg text-slate-800 flex items-center">
                        <i class="fa-solid fa-database text-indigo-600 mr-2"></i> Enlaces Vinculados Activos
                    </h3>
                    <p class="text-xs text-slate-500">Estos enlaces se conectan directamente cuando el estudiante hace clic en "Ver Guía PDF".</p>
                    <div id="admin-drive-list" class="space-y-2 max-h-60 overflow-y-auto pr-1">
                        <!-- Populated via JS -->
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- MODAL: PDF Viewer / Google Drive Integration -->
    <div id="pdf-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white w-full max-w-4xl h-[85vh] rounded-2xl shadow-2xl flex flex-col overflow-hidden animate-in">
            <div class="bg-indigo-900 text-white px-6 py-4 flex justify-between items-center">
                <div class="flex items-center space-x-3">
                    <i class="fa-brands fa-google-drive text-blue-400 text-2xl"></i>
                    <div>
                        <h3 id="modal-pdf-title" class="font-bold text-base">Guía de Estudio sincronizada con Drive</h3>
                        <span class="text-xs text-indigo-300">Visualizador Oficial Exámenes Libres</span>
                    </div>
                </div>
                <button onclick="closePdfModal()" class="text-indigo-200 hover:text-white p-2 rounded-lg hover:bg-indigo-800">
                    <i class="fa-solid fa-xmark text-xl"></i>
                </button>
            </div>
            <div class="flex-grow overflow-y-auto p-6 sm:p-10 bg-slate-100 space-y-6">
                <div class="bg-white p-8 rounded-xl shadow-sm border border-slate-200 max-w-3xl mx-auto space-y-6 text-center">
                    <div class="w-16 h-16 bg-blue-50 text-blue-600 rounded-full flex items-center justify-center mx-auto text-3xl">
                        <i class="fa-brands fa-google-drive"></i>
                    </div>
                    <h4 id="pdf-inner-heading" class="text-xl font-extrabold text-slate-900">Documento en Google Drive</h4>
                    <p class="text-slate-600 text-sm max-w-md mx-auto">Este material está alojado de forma segura en Google Drive para garantizar una descarga rápida y sin interrupciones.</p>
                    
                    <div class="pt-4">
                        <a id="modal-drive-link-btn" href="#" target="_blank" class="inline-flex items-center bg-indigo-600 hover:bg-indigo-700 text-white font-bold px-6 py-3.5 rounded-xl transition shadow">
                            <i class="fa-solid fa-external-link-alt mr-2"></i> Abrir Guía Completa en Google Drive
                        </a>
                    </div>
                </div>
            </div>
            <div class="bg-white px-6 py-4 border-t border-slate-200 flex justify-between items-center">
                <span class="text-xs text-slate-500"><i class="fa-solid fa-lock text-emerald-600 mr-1"></i> Contenido protegido para estudiantes AulaLibre</span>
                <button onclick="closePdfModal()" class="bg-slate-200 hover:bg-slate-300 text-slate-800 text-xs font-semibold px-5 py-2.5 rounded-xl transition">
                    Cerrar Visor
                </button>
            </div>
        </div>
    </div>

    <!-- MODAL: Interactive Test / Evaluation -->
    <div id="test-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white w-full max-w-2xl rounded-2xl shadow-2xl flex flex-col overflow-hidden animate-in">
            <div class="bg-indigo-900 text-white px-6 py-4 flex justify-between items-center">
                <div class="flex items-center space-x-3">
                    <i class="fa-solid fa-square-poll-vertical text-amber-400 text-2xl"></i>
                    <div>
                        <h3 id="test-modal-title" class="font-bold text-base">Evaluación de Ensayo OA</h3>
                        <span class="text-xs text-indigo-300">Corrección Instantánea</span>
                    </div>
                </div>
                <button onclick="closeTestModal()" class="text-indigo-200 hover:text-white p-2 rounded-lg hover:bg-indigo-800">
                    <i class="fa-solid fa-xmark text-xl"></i>
                </button>
            </div>
            <div id="test-body" class="p-6 sm:p-8 space-y-6 max-h-[70vh] overflow-y-auto"></div>
            <div id="test-footer" class="bg-slate-50 px-6 py-4 border-t border-slate-200 flex justify-between items-center">
                <span id="test-progress-indicator" class="text-xs font-bold text-slate-500">Pregunta 1 de 3</span>
                <button id="test-next-btn" onclick="nextTestQuestion()" class="bg-indigo-600 hover:bg-indigo-700 text-white font-semibold text-xs px-5 py-2.5 rounded-xl transition">
                    Siguiente Pregunta
                </button>
            </div>
        </div>
    </div>

    <!-- MODAL: Checkout / Upgrade -->
    <div id="checkout-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white w-full max-w-md rounded-2xl shadow-2xl p-6 sm:p-8 space-y-6 animate-in relative">
            <button onclick="closeCheckoutModal()" class="absolute top-4 right-4 text-slate-400 hover:text-slate-600">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>
            <div class="text-center space-y-2">
                <div class="w-12 h-12 bg-amber-100 text-amber-600 rounded-2xl flex items-center justify-center mx-auto text-2xl font-bold">
                    <i class="fa-solid fa-crown"></i>
                </div>
                <h3 class="text-xl font-extrabold text-slate-900">Pase Anual Exámenes Libres Pro</h3>
                <p class="text-slate-500 text-xs leading-relaxed">Desbloquea los 12 cursos completos, guías ilimitadas de Google Drive y ensayos tipo MINEDUC.</p>
            </div>
            <div class="bg-slate-50 p-4 rounded-xl border border-slate-200 space-y-2 text-xs">
                <div class="flex items-center text-slate-700"><i class="fa-solid fa-check text-emerald-600 mr-2"></i> Acceso ilimitado a los 12 niveles (1°B a 4°M)</div>
                <div class="flex items-center text-slate-700"><i class="fa-solid fa-check text-emerald-600 mr-2"></i> Enlaces directos a carpetas de Google Drive</div>
                <div class="flex items-center text-slate-700"><i class="fa-solid fa-check text-emerald-600 mr-2"></i> Soporte oficial temporada 2026</div>
            </div>
            <button onclick="completePurchase()" class="w-full bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-3 rounded-xl transition shadow-lg flex items-center justify-center">
                <i class="fa-solid fa-lock mr-2"></i> Pagar con MercadoPago / WebPay ($29.990)
            </button>
            <p class="text-center text-[10px] text-slate-400">Garantía de devolución de 7 días. Activación inmediata.</p>
        </div>
    </div>

    <!-- Toast Notification -->
    <div id="toast" class="fixed bottom-5 right-5 bg-slate-900 text-white px-4 py-3 rounded-xl shadow-2xl transform translate-y-20 opacity-0 transition-all duration-300 z-50 flex items-center space-x-3 text-sm">
        <i id="toast-icon" class="fa-solid fa-circle-check text-emerald-400 text-lg"></i>
        <span id="toast-message">Mensaje de notificación</span>
    </div>

    <!-- JavaScript Logic: 12 Courses & Google Drive Integration -->
    <script>
        // Data Structure with all 12 Grades (1° Básico to 4° Medio) and 5-6 Subjects each
        const virtualData = {
            "1basico": { name: "1° Básico", subjects: getStandardSubjects("1° Básico") },
            "2basico": { name: "2° Básico", subjects: getStandardSubjects("2° Básico") },
            "3basico": { name: "3° Básico", subjects: getStandardSubjects("3° Básico") },
            "4basico": { name: "4° Básico", subjects: getStandardSubjects("4° Básico") },
            "5basico": { name: "5° Básico", subjects: getStandardSubjects("5° Básico") },
            "6basico": { name: "6° Básico", subjects: getStandardSubjects("6° Básico") },
            "7basico": { name: "7° Básico", subjects: getStandardSubjects("7° Básico") },
            "8basico": { name: "8° Básico", subjects: getStandardSubjects("8° Básico") },
            "1medio":  { name: "1° Medio", subjects: getStandardSubjects("1° Medio") },
            "2medio":  { name: "2° Medio", subjects: getStandardSubjects("2° Medio") },
            "3medio":  { name: "3° Medio", subjects: getStandardSubjects("3° Medio") },
            "4medio":  { name: "4° Medio", subjects: getStandardSubjects("4° Medio") }
        };

        // Helper to generate 5-6 standard MINEDUC subjects for any grade
        function getStandardSubjects(gradeName) {
            return [
                {
                    id: "mat",
                    name: "Matemática",
                    icon: "fa-calculator",
                    units: [
                        {
                            title: `Unidad 1: Números y Operaciones (${gradeName})`,
                            oaList: [{ code: "OA 1", desc: "Comprender y aplicar conceptos fundamentales de la asignatura según temario MINEDUC." }],
                            guides: [{ title: `Guía Oficial Drive - ${gradeName}`, type: "PDF Google Drive", url: "https://drive.google.com" }],
                            test: {
                                title: `Ensayo Práctico Matemática - ${gradeName}`,
                                questions: [
                                    { q: "¿Cuál es el concepto central evaluado en esta unidad?", options: ["Operatoria básica", "Análisis avanzado", "Geometría plana", "Estadística"], correct: 0 }
                                ]
                            }
                        }
                    ]
                },
                {
                    id: "leng",
                    name: "Lenguaje y Comunicación",
                    icon: "fa-book-open",
                    units: [
                        {
                            title: `Unidad 1: Comprensión Lectora y Escritura`,
                            oaList: [{ code: "OA 3", desc: "Leer y analizar textos informativos y literarios con enfoque de examen libre." }],
                            guides: [{ title: `Guía Lectura y Comprensión (${gradeName})`, type: "PDF Google Drive", url: "https://drive.google.com" }],
                            test: {
                                title: `Ensayo Comprensión Lectora - ${gradeName}`,
                                questions: [
                                    { q: "¿Cuál es el propósito del texto principal?", options: ["Informar", "Entretener", "Persuadir", "Instruir"], correct: 0 }
                                ]
                            }
                        }
                    ]
                },
                {
                    id: "cie",
                    name: "Ciencias Naturales / Biología",
                    icon: "fa-flask",
                    units: [
                        {
                            title: `Unidad 1: Entorno Natural y Científico`,
                            oaList: [{ code: "OA 2", desc: "Explicar fenómenos naturales y científicos del nivel correspondiente." }],
                            guides: [{ title: `Guía de Ciencias (${gradeName})`, type: "PDF Google Drive", url: "https://drive.google.com" }],
                            test: {
                                title: `Test de Ciencias - ${gradeName}`,
                                questions: [
                                    { q: "¿Qué método científico se aplica en la investigación?", options: ["Observación y experimentación", "Suposición", "Azar", "Ninguna"], correct: 0 }
                                ]
                            }
                        }
                    ]
                },
                {
                    id: "hist",
                    name: "Historia, Geografía y Cs. Sociales",
                    icon: "fa-landmark",
                    units: [
                        {
                            title: `Unidad 1: Sociedad, Territorio y Cultura`,
                            oaList: [{ code: "OA 4", desc: "Reconocer procesos históricos y organización social y cívica." }],
                            guides: [{ title: `Guía de Historia y Sociedad (${gradeName})`, type: "PDF Google Drive", url: "https://drive.google.com" }],
                            test: {
                                title: `Ensayo Historia - ${gradeName}`,
                                questions: [
                                    { q: "¿Qué factor geográfico influye en el desarrollo local?", options: ["Relieve y clima", "Moneda", "Tecnología", "Idioma"], correct: 0 }
                                ]
                            }
                        }
                    ]
                },
                {
                    id: "ing",
                    name: "Inglés",
                    icon: "fa-language",
                    units: [
                        {
                            title: `Unidad 1: Basic Vocabulary & Reading`,
                            oaList: [{ code: "OA 5", desc: "Comprender textos breves y vocabulario fundamental en inglés." }],
                            guides: [{ title: `Guía de Inglés (${gradeName})`, type: "PDF Google Drive", url: "https://drive.google.com" }],
                            test: {
                                title: `Test de Inglés - ${gradeName}`,
                                questions: [
                                    { q: "Choose the correct pronoun for 'Maria':", options: ["She", "He", "They", "It"], correct: 0 }
                                ]
                            }
                        }
                    ]
                },
                {
                    id: "tec",
                    name: "Tecnología / Educ. Ciudadana",
                    icon: "fa-laptop-code",
                    units: [
                        {
                            title: `Unidad 1: Alfabetización Digital y Ciudadanía`,
                            oaList: [{ code: "OA 6", desc: "Desarrollar habilidades tecnológicas y de participación ciudadana." }],
                            guides: [{ title: `Guía de Apoyo Complementario (${gradeName})`, type: "PDF Google Drive", url: "https://drive.google.com" }],
                            test: {
                                title: `Evaluación Final - ${gradeName}`,
                                questions: [
                                    { q: "¿Cuál es un derecho ciudadano fundamental?", options: ["Participación y respeto", "Aislamiento", "Ninguno", "Obligación ciego"], correct: 0 }
                                ]
                            }
                        }
                    ]
                }
            ];
        }

        let currentGradeKey = "2medio";
        let currentSubjectId = "mat";
        let activeTestObj = null;
        let currentQuestionIdx = 0;
        let userAnswers = {};

        window.onload = function() {
            populateGradeDropdowns();
            renderHomeCoursesGrid();
            renderSubjects();
            renderSubjectDetail();
            populateAdminDropdown();
            renderAdminDriveList();
        };

        function switchTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(el => el.classList.add('hidden'));
            document.getElementById(`tab-${tabId}`).classList.remove('hidden');

            document.querySelectorAll('.nav-btn').forEach(btn => {
                btn.classList.remove('bg-indigo-800', 'text-white');
                btn.classList.add('text-indigo-200');
            });
            const activeBtn = document.getElementById(`nav-${tabId}`);
            if (activeBtn) {
                activeBtn.classList.add('bg-indigo-800', 'text-white');
                activeBtn.classList.remove('text-indigo-200');
            }
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function toggleMobileMenu() {
            document.getElementById('mobile-menu').classList.toggle('hidden');
        }

        function populateGradeDropdowns() {
            const select = document.getElementById('grade-select');
            select.innerHTML = '';
            for (const [key, grade] of Object.entries(virtualData)) {
                const opt = document.createElement('option');
                opt.value = key;
                opt.textContent = grade.name;
                if (key === currentGradeKey) opt.selected = true;
                select.appendChild(opt);
            }
        }

        function populateAdminDropdown() {
            const select = document.getElementById('drive-course-target');
            select.innerHTML = '';
            for (const [key, grade] of Object.entries(virtualData)) {
                const opt = document.createElement('option');
                opt.value = key;
                opt.textContent = grade.name;
                select.appendChild(opt);
            }
        }

        function renderHomeCoursesGrid() {
            const grid = document.getElementById('home-courses-grid');
            grid.innerHTML = '';
            for (const [key, grade] of Object.entries(virtualData)) {
                const card = document.createElement('div');
                card.className = "bg-white p-5 rounded-xl shadow-sm border border-slate-200 hover:border-indigo-500 hover:shadow-md transition cursor-pointer group";
                card.onclick = () => {
                    currentGradeKey = key;
                    document.getElementById('grade-select').value = key;
                    onGradeChange(key);
                    switchTab('courses');
                };
                card.innerHTML = `
                    <div class="w-9 h-9 rounded-lg bg-indigo-50 text-indigo-600 flex items-center justify-center font-bold mb-2 group-hover:bg-indigo-600 group-hover:text-white transition text-xs"><i class="fa-solid fa-graduation-cap"></i></div>
                    <h3 class="font-bold text-slate-800 text-sm mb-1">${grade.name}</h3>
                    <p class="text-slate-400 text-[11px] mb-3">6 Asignaturas • Drive</p>
                    <span class="text-xs font-semibold text-indigo-600 group-hover:underline">Ver curso &rarr;</span>
                `;
                grid.appendChild(card);
            }
        }

        function onGradeChange(gradeKey) {
            currentGradeKey = gradeKey;
            const subjects = virtualData[gradeKey].subjects;
            currentSubjectId = subjects.length > 0 ? subjects[0].id : null;
            renderSubjects();
            renderSubjectDetail();
            showToast(`Cambiado a ${virtualData[gradeKey].name}`, 'info');
        }

        function renderSubjects() {
            const listEl = document.getElementById('subjects-list');
            listEl.innerHTML = '';
            const grade = virtualData[currentGradeKey];
            if (!grade || !grade.subjects) return;

            grade.subjects.forEach(sub => {
                const isSelected = sub.id === currentSubjectId;
                const btn = document.createElement('button');
                btn.className = `w-full text-left px-3.5 py-2.5 rounded-xl text-xs font-semibold transition flex items-center justify-between ${
                    isSelected ? 'bg-indigo-600 text-white shadow-md' : 'bg-white text-slate-700 hover:bg-slate-100 border border-slate-200'
                }`;
                btn.innerHTML = `<span class="flex items-center"><i class="fa-solid ${sub.icon} w-5 mr-2"></i> ${sub.name}</span><i class="fa-solid fa-chevron-right text-[10px] opacity-60"></i>`;
                btn.onclick = () => {
                    currentSubjectId = sub.id;
                    renderSubjects();
                    renderSubjectDetail();
                };
                listEl.appendChild(btn);
            });
        }

        function renderSubjectDetail() {
            const container = document.getElementById('subject-detail-view');
            const grade = virtualData[currentGradeKey];
            if (!grade) return;
            const subject = grade.subjects.find(s => s.id === currentSubjectId);
            if (!subject) return;

            let html = `
                <div class="border-b border-slate-100 pb-5 mb-6">
                    <span class="text-xs font-bold uppercase tracking-wider text-indigo-600 bg-indigo-50 px-3 py-1 rounded-full">${grade.name}</span>
                    <h3 class="text-2xl font-extrabold text-slate-900 mt-2 flex items-center"><i class="fa-solid ${subject.icon} mr-3 text-indigo-600"></i>${subject.name}</h3>
                    <p class="text-slate-500 text-sm mt-1">Guías oficiales conectadas con Google Drive y Objetivos MINEDUC.</p>
                </div>
                <div class="space-y-6">
            `;

            subject.units.forEach((unit, uIdx) => {
                html += `
                    <div class="bg-slate-50 border border-slate-200 rounded-2xl p-6 space-y-4">
                        <div class="flex justify-between items-center">
                            <h4 class="font-bold text-slate-900 text-base flex items-center">
                                <span class="bg-indigo-600 text-white w-7 h-7 rounded-lg flex items-center justify-center text-xs mr-2.5 shadow-sm">${uIdx + 1}</span>
                                ${unit.title}
                            </h4>
                            <span class="text-xs font-semibold text-slate-500 bg-white px-3 py-1 rounded-lg border border-slate-200">Oficial MINEDUC</span>
                        </div>
                        
                        <div class="space-y-2 pl-2">
                            <span class="text-xs font-bold text-slate-400 uppercase tracking-wider">Objetivos de Aprendizaje (OA)</span>
                            <div class="grid grid-cols-1 gap-2">
                `;
                unit.oaList.forEach(oa => {
                    html += `
                        <div class="bg-white p-3.5 rounded-xl border border-slate-200 flex items-start space-x-3 text-sm">
                            <span class="bg-indigo-50 text-indigo-700 font-bold px-2 py-0.5 rounded text-xs shrink-0">${oa.code}</span>
                            <p class="text-slate-700 text-xs sm:text-sm leading-relaxed">${oa.desc}</p>
                        </div>
                    `;
                });
                html += `</div></div>`;

                html += `
                        <div class="pt-3 border-t border-slate-200 flex flex-wrap gap-3 items-center justify-between">
                            <div class="flex flex-wrap gap-2">
                `;
                unit.guides.forEach(g => {
                    html += `
                        <button onclick="openPdfModal('${g.title}', '${g.url}')" class="bg-white hover:bg-indigo-50 text-indigo-700 border border-indigo-200 font-semibold text-xs px-3.5 py-2.5 rounded-xl transition flex items-center shadow-sm">
                            <i class="fa-brands fa-google-drive text-blue-500 mr-2 text-sm"></i> ${g.title}
                        </button>
                    `;
                });
                html += `
                            </div>
                            <div>
                                <button onclick='startTest(${JSON.stringify(unit.test)})' class="bg-indigo-600 hover:bg-indigo-700 text-white font-semibold text-xs px-4 py-2.5 rounded-xl transition shadow flex items-center">
                                    <i class="fa-solid fa-square-poll-vertical mr-2"></i> Iniciar Ensayo Test
                                </button>
                            </div>
                        </div>
                    </div>
                `;
            });

            html += `</div>`;
            container.innerHTML = html;
        }

        function openPdfModal(guideTitle, driveUrl) {
            document.getElementById('modal-pdf-title').textContent = guideTitle;
            document.getElementById('pdf-inner-heading').textContent = guideTitle;
            document.getElementById('modal-drive-link-btn').href = driveUrl || "https://drive.google.com";
            document.getElementById('pdf-modal').classList.remove('hidden');
        }

        function closePdfModal() {
            document.getElementById('pdf-modal').classList.add('hidden');
        }

        function startTest(testObj) {
            activeTestObj = testObj;
            currentQuestionIdx = 0;
            userAnswers = {};
            document.getElementById('test-modal-title').textContent = testObj.title;
            renderTestQuestion();
            document.getElementById('test-modal').classList.remove('hidden');
        }

        function closeTestModal() {
            document.getElementById('test-modal').classList.add('hidden');
        }

        function renderTestQuestion() {
            const body = document.getElementById('test-body');
            document.getElementById('test-footer').style.display = 'flex';
            const q = activeTestObj.questions[currentQuestionIdx];

            document.getElementById('test-progress-indicator').textContent = `Pregunta ${currentQuestionIdx + 1} de ${activeTestObj.questions.length}`;

            let html = `
                <div class="space-y-4">
                    <div class="bg-indigo-50 text-indigo-900 font-semibold p-4 rounded-xl text-sm border border-indigo-100">
                        ${q.q}
                    </div>
                    <div class="space-y-2">
            `;
            q.options.forEach((opt, idx) => {
                const isSelected = userAnswers[currentQuestionIdx] === idx;
                html += `
                    <button onclick="selectOption(${idx})" class="w-full text-left p-3.5 rounded-xl border text-sm font-medium transition flex items-center justify-between ${
                        isSelected ? 'bg-indigo-600 text-white border-indigo-600 shadow-sm' : 'bg-white text-slate-700 border-slate-200 hover:bg-slate-50'
                    }">
                        <span><strong class="mr-2">${String.fromCharCode(65 + idx)}.</strong> ${opt}</span>
                        ${isSelected ? '<i class="fa-solid fa-circle-check"></i>' : ''}
                    </button>
                `;
            });
            html += `</div></div>`;
            body.innerHTML = html;

            const isLast = currentQuestionIdx === activeTestObj.questions.length - 1;
            document.getElementById('test-next-btn').textContent = isLast ? 'Finalizar y Ver Nota' : 'Siguiente Pregunta';
        }

        function selectOption(idx) {
            userAnswers[currentQuestionIdx] = idx;
            renderTestQuestion();
        }

        function nextTestQuestion() {
            if (userAnswers[currentQuestionIdx] === undefined) {
                showToast('Por favor selecciona una alternativa', 'error');
                return;
            }
            if (currentQuestionIdx < activeTestObj.questions.length - 1) {
                currentQuestionIdx++;
                renderTestQuestion();
            } else {
                let correctCount = 0;
                activeTestObj.questions.forEach((q, idx) => {
                    if (userAnswers[idx] === q.correct) correctCount++;
                });
                const percentage = Math.round((correctCount / activeTestObj.questions.length) * 100);
                
                document.getElementById('test-body').innerHTML = `
                    <div class="text-center py-6 space-y-4">
                        <div class="w-16 h-16 bg-emerald-100 text-emerald-600 rounded-full flex items-center justify-center mx-auto text-3xl font-bold">
                            <i class="fa-solid fa-award"></i>
                        </div>
                        <h4 class="text-2xl font-extrabold text-slate-900">¡Práctica Finalizada con Éxito!</h4>
                        <p class="text-slate-600 text-sm">Tu puntaje obtenido es de:</p>
                        <div class="text-4xl font-extrabold text-indigo-600">${correctCount} / ${activeTestObj.questions.length} (${percentage}%)</div>
                        <button onclick="closeTestModal()" class="bg-indigo-600 hover:bg-indigo-700 text-white font-semibold px-6 py-3 rounded-xl transition shadow">
                            Continuar Estudiando
                        </button>
                    </div>
                `;
                document.getElementById('test-footer').style.display = 'none';
            }
        }

        function openCheckoutModal() { document.getElementById('checkout-modal').classList.remove('hidden'); }
        function closeCheckoutModal() { document.getElementById('checkout-modal').classList.add('hidden'); }
        function completePurchase() {
            closeCheckoutModal();
            showToast('¡Pago exitoso! Membresía Pro activada para los 12 cursos.', 'success');
        }

        // Admin Drive Link Handler
        let customDriveLinks = [
            { course: "2° Medio", title: "Guía Oficial Drive - Matemáticas", url: "https://drive.google.com" }
        ];

        function handleDriveLinkSubmit(event) {
            event.preventDefault();
            const courseKey = document.getElementById('drive-course-target').value;
            const title = document.getElementById('drive-guide-title').value;
            const url = document.getElementById('drive-url-input').value;

            const gradeObj = virtualData[courseKey];
            if (gradeObj && gradeObj.subjects.length > 0) {
                gradeObj.subjects[0].units[0].guides.push({ title: title, type: "PDF Google Drive", url: url });
            }

            customDriveLinks.push({ course: gradeObj.name, title: title, url: url });
            renderAdminDriveList();
            renderSubjectDetail();
            document.getElementById('admin-drive-form').reset();
            showToast(`Enlace de Google Drive vinculado a ${gradeObj.name}`, 'success');
        }

        function renderAdminDriveList() {
            const listEl = document.getElementById('admin-drive-list');
            listEl.innerHTML = '';
            customDriveLinks.forEach(link => {
                const item = document.createElement('div');
                item.className = "bg-slate-50 border border-slate-200 p-3 rounded-xl flex items-center justify-between text-xs";
                item.innerHTML = `
                    <div>
                        <span class="font-bold text-indigo-700">${link.course}</span> &bull; 
                        <span class="font-medium text-slate-800">${link.title}</span>
                    </div>
                    <span class="bg-blue-100 text-blue-800 px-2 py-0.5 rounded-full font-semibold">Drive OK</span>
                `;
                listEl.appendChild(item);
            });
        }

        let toastTimeoutId = null;
        function showToast(message, type = 'success') {
            const toast = document.getElementById('toast');
            const msg = document.getElementById('toast-message');
            const icon = document.getElementById('toast-icon');

            msg.textContent = message;
            icon.className = type === 'success' ? "fa-solid fa-circle-check text-emerald-400 text-lg" : "fa-solid fa-circle-info text-indigo-400 text-lg";

            toast.classList.remove('translate-y-20', 'opacity-0');
            if (toastTimeoutId) clearTimeout(toastTimeoutId);
            toastTimeoutId = setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 3500);
        }
    </script>
</body>
</html>
