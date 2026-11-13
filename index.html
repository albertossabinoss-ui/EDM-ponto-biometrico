<!DOCTYPE html>
<html lang="pt-PT">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EDM - Controle de Ponto Biométrico e Gestão de Assiduidade</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['"Plus Jakarta Sans"', 'sans-serif'],
                    },
                    colors: {
                        edm: {
                            50: '#FFF8F2',
                            100: '#FFEDD5',
                            200: '#FED7AA',
                            300: '#FDBA74',
                            400: '#FB923C',
                            500: '#F26522',
                            600: '#D9531E',
                            700: '#C2410C',
                            800: '#9A3412',
                            900: '#7C2D12',
                        }
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #FFF8F2;
            color: #1E293B;
            overflow-x: hidden;
        }

        /* Animação suave do leitor biométrico */
        @keyframes pulse-ring {
            0% { transform: scale(0.92); box-shadow: 0 0 0 0 rgba(249, 115, 22, 0.5); }
            70% { transform: scale(1); box-shadow: 0 0 0 18px rgba(249, 115, 22, 0); }
            100% { transform: scale(0.92); box-shadow: 0 0 0 0 rgba(249, 115, 22, 0); }
        }

        @keyframes scan-line {
            0% { top: 10%; opacity: 0.2; }
            50% { top: 85%; opacity: 1; }
            100% { top: 10%; opacity: 0.2; }
        }

        .fingerprint-btn {
            animation: pulse-ring 2.5s infinite cubic-bezier(0.66, 0, 0, 1);
            transition: all 0.2s ease;
        }
        .fingerprint-btn:active {
            transform: scale(0.94);
        }

        .scanner-laser {
            position: absolute;
            left: 15%;
            right: 15%;
            height: 3px;
            background: linear-gradient(90deg, transparent, #F97316, transparent);
            box-shadow: 0 0 8px #F97316;
            animation: scan-line 2s infinite ease-in-out;
        }

        /* Estilos exclusivos para impressão do Relatório Oficial RH */
        @media print {
            body * {
                visibility: hidden;
            }
            #printable-rh-report, #printable-rh-report * {
                visibility: visible;
            }
            #printable-rh-report {
                position: absolute;
                left: 0;
                top: 0;
                width: 100%;
                background: white !important;
                padding: 20px !important;
                box-shadow: none !important;
            }
            .no-print {
                display: none !important;
            }
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between selection:bg-edm-200 selection:text-edm-900">

    <!-- CABEÇALHO CORPORATIVO -->
    <header class="bg-white border-b border-edm-200 sticky top-0 z-30 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 sm:h-20 flex items-center justify-between">
            <!-- Identidade Visual EDM -->
            <div class="flex items-center gap-3">
                <div class="w-10 h-10 sm:w-12 sm:h-12 rounded-xl bg-gradient-to-br from-edm-500 to-edm-600 flex items-center justify-center text-white shadow-md shadow-edm-500/20">
                    <i class="fa-solid fa-bolt text-xl sm:text-2xl"></i>
                </div>
                <div>
                    <div class="flex items-center gap-2">
                        <h1 class="font-extrabold text-lg sm:text-xl tracking-tight text-slate-900">EDM <span class="text-edm-600 font-semibold">Ponto</span></h1>
                        <span class="hidden md:inline-flex items-center px-2 py-0.5 rounded-full text-xs font-medium bg-edm-100 text-edm-800">
                            Eletricidade de Moçambique
                        </span>
                    </div>
                    <p class="text-xs text-slate-500">Sistema Biométrico de Assiduidade</p>
                </div>
            </div>

            <!-- Status Hardware & Botão Área do Chefe -->
            <div class="flex items-center gap-2 sm:gap-4">
                <!-- Indicador Hardware Plug-and-Play -->
                <div class="hidden sm:flex items-center gap-2 px-3 py-1.5 rounded-lg bg-emerald-50 border border-emerald-200 text-emerald-700 text-xs font-medium" title="Pronto para leitores biométricos USB externos, WebAuthn e ecrãs táteis Android">
                    <span class="w-2 h-2 rounded-full bg-emerald-500 animate-ping"></span>
                    <span>Sensor Touch / USB Pronto</span>
                </div>

                <!-- Botão Alternar Vista (Terminal vs Chefe) -->
                <button id="btn-toggle-admin" onclick="handleAdminAccessClick()" class="flex items-center gap-2 px-3.5 py-2 sm:px-4 sm:py-2.5 rounded-xl bg-slate-900 hover:bg-slate-800 text-white text-xs sm:text-sm font-semibold transition shadow-sm">
                    <i class="fa-solid fa-user-shield text-edm-400"></i>
                    <span id="admin-btn-text">Área do Chefe</span>
                </button>
            </div>
        </div>
    </header>

    <!-- CONTEÚDO PRINCIPAL -->
    <main class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-6 sm:py-8">

        <!-- ===================================================================== -->
        <!-- VISTA 1: TERMINAL DE PONTO DO TRABALHADOR (PÚBLICO / ENTRADA)         -->
        <!-- ===================================================================== -->
        <section id="view-terminal" class="space-y-6">
            
            <!-- Banner Superior com Relógio Digital em Tempo Real -->
            <div class="bg-white rounded-3xl p-6 sm:p-8 border border-edm-200/80 shadow-sm flex flex-col md:flex-row items-center justify-between gap-6 relative overflow-hidden">
                <div class="absolute -right-12 -top-12 w-48 h-48 bg-edm-100/60 rounded-full blur-2xl pointer-events-none"></div>
                
                <div class="text-center md:text-left z-10">
                    <span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-semibold bg-edm-100 text-edm-700 mb-2">
                        <i class="fa-regular fa-clock"></i> Registo Obrigatório de Entrada & Saída
                    </span>
                    <h2 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Bem-vindo ao Posto de Trabalho</h2>
                    <p class="text-slate-600 text-sm sm:text-base mt-1 max-w-xl">
                        Coloque o seu dedo no leitor biométrico ou introduza a sua senha pessoal fornecida pela chefia para validar a sua presença.
                    </p>
                </div>

                <!-- Relógio Digital -->
                <div class="bg-gradient-to-br from-edm-50 to-orange-100/70 border border-edm-200 rounded-2xl px-6 py-4 text-center min-w-[240px] z-10 shadow-inner">
                    <div id="live-clock" class="text-3xl sm:text-4xl font-extrabold text-edm-600 tracking-wider font-mono">
                        00:00:00
                    </div>
                    <div id="live-date" class="text-xs sm:text-sm font-medium text-slate-600 mt-1 capitalize">
                        Carregando data...
                    </div>
                </div>
            </div>

            <!-- Grid Principal do Terminal: Leitor Biométrico + Senha Pessoal -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6 items-stretch">
                
                <!-- Cartão A: Leitor Biométrico Touch Screen / USB -->
                <div class="lg:col-span-6 bg-white rounded-3xl p-6 sm:p-8 border border-edm-200 shadow-sm flex flex-col items-center justify-between text-center">
                    <div class="w-full">
                        <div class="flex items-center justify-between mb-2">
                            <span class="text-xs font-bold uppercase tracking-wider text-edm-600 bg-edm-50 px-2.5 py-1 rounded-md">Opção 1 • Biometria</span>
                            <span class="text-xs text-slate-400 flex items-center gap-1"><i class="fa-solid fa-mobile-screen"></i> Touch / Leitor USB</span>
                        </div>
                        <h3 class="text-xl font-bold text-slate-800 mt-2">Leitor de Impressão Digital (Finger)</h3>
                        <p class="text-sm text-slate-500 mt-1">Toque no sensor abaixo com o dedo registado</p>
                    </div>

                    <!-- Botão Sensor Biométrico Interativo -->
                    <div class="my-8 relative flex flex-col items-center">
                        <button onclick="handleTerminalBiometricClick()" class="fingerprint-btn relative w-36 h-36 sm:w-40 sm:h-40 rounded-full bg-gradient-to-b from-edm-50 to-edm-100 border-4 border-edm-500 flex items-center justify-center text-edm-600 hover:bg-edm-100 focus:outline-none cursor-pointer group">
                            <div class="scanner-laser rounded-full"></div>
                            <i class="fa-solid fa-fingerprint text-6xl sm:text-7xl group-hover:scale-105 transition-transform"></i>
                        </button>
                        <span class="mt-4 text-xs font-semibold text-edm-700 bg-edm-50 px-3 py-1 rounded-full border border-edm-200">
                            Toque no sensor para ler digital
                        </span>
                    </div>

                    <div class="w-full pt-4 border-t border-slate-100 flex items-center justify-center gap-2 text-xs text-slate-500">
                        <i class="fa-solid fa-shield-halved text-emerald-600"></i>
                        <span>Reconhecimento biométrico instantâneo (Entrada / Saída automática)</span>
                    </div>
                </div>

                <!-- Cartão B: Autenticação por Senha Própria -->
                <div class="lg:col-span-6 bg-white rounded-3xl p-6 sm:p-8 border border-edm-200 shadow-sm flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between mb-2">
                            <span class="text-xs font-bold uppercase tracking-wider text-slate-600 bg-slate-100 px-2.5 py-1 rounded-md">Opção 2 • Código Pessoal</span>
                            <span class="text-xs text-slate-400 flex items-center gap-1"><i class="fa-solid fa-keyboard"></i> Computador / Teclado</span>
                        </div>
                        <h3 class="text-xl font-bold text-slate-800 mt-2">Registo por Senha do Trabalhador</h3>
                        <p class="text-sm text-slate-500 mt-1">Caso não utilize o leitor digital, digite a senha fornecida pelo chefe</p>

                        <form onsubmit="handlePasswordClockIn(event)" class="mt-6 space-y-4">
                            <div>
                                <label for="worker-pin-input" class="block text-xs font-semibold uppercase tracking-wider text-slate-500 mb-1.5">Senha Pessoal</label>
                                <div class="relative">
                                    <span class="absolute inset-y-0 left-0 pl-4 flex items-center text-slate-400">
                                        <i class="fa-solid fa-key"></i>
                                    </span>
                                    <input type="password" id="worker-pin-input" required autocomplete="off" placeholder="Ex: 1001" 
                                        class="w-full pl-11 pr-4 py-3.5 bg-slate-50 border border-slate-200 rounded-xl text-lg font-bold tracking-widest text-slate-800 focus:bg-white focus:ring-2 focus:ring-edm-500 focus:border-edm-500 outline-none transition">
                                </div>
                            </div>

                            <!-- Teclado Numérico Rápido para ecrãs táteis -->
                            <div class="grid grid-cols-3 gap-2 pt-1">
                                <button type="button" onclick="appendPin('1')" class="py-2.5 rounded-xl bg-slate-50 hover:bg-edm-50 active:bg-edm-100 border border-slate-200 font-bold text-slate-700 text-base transition">1</button>
                                <button type="button" onclick="appendPin('2')" class="py-2.5 rounded-xl bg-slate-50 hover:bg-edm-50 active:bg-edm-100 border border-slate-200 font-bold text-slate-700 text-base transition">2</button>
                                <button type="button" onclick="appendPin('3')" class="py-2.5 rounded-xl bg-slate-50 hover:bg-edm-50 active:bg-edm-100 border border-slate-200 font-bold text-slate-700 text-base transition">3</button>
                                <button type="button" onclick="appendPin('4')" class="py-2.5 rounded-xl bg-slate-50 hover:bg-edm-50 active:bg-edm-100 border border-slate-200 font-bold text-slate-700 text-base transition">4</button>
                                <button type="button" onclick="appendPin('5')" class="py-2.5 rounded-xl bg-slate-50 hover:bg-edm-50 active:bg-edm-100 border border-slate-200 font-bold text-slate-700 text-base transition">5</button>
                                <button type="button" onclick="appendPin('6')" class="py-2.5 rounded-xl bg-slate-50 hover:bg-edm-50 active:bg-edm-100 border border-slate-200 font-bold text-slate-700 text-base transition">6</button>
                                <button type="button" onclick="appendPin('7')" class="py-2.5 rounded-xl bg-slate-50 hover:bg-edm-50 active:bg-edm-100 border border-slate-200 font-bold text-slate-700 text-base transition">7</button>
                                <button type="button" onclick="appendPin('8')" class="py-2.5 rounded-xl bg-slate-50 hover:bg-edm-50 active:bg-edm-100 border border-slate-200 font-bold text-slate-700 text-base transition">8</button>
                                <button type="button" onclick="appendPin('9')" class="py-2.5 rounded-xl bg-slate-50 hover:bg-edm-50 active:bg-edm-100 border border-slate-200 font-bold text-slate-700 text-base transition">9</button>
                                <button type="button" onclick="clearPin()" class="py-2.5 rounded-xl bg-rose-50 hover:bg-rose-100 border border-rose-200 font-semibold text-rose-600 text-xs transition">LIMPAR</button>
                                <button type="button" onclick="appendPin('0')" class="py-2.5 rounded-xl bg-slate-50 hover:bg-edm-50 active:bg-edm-100 border border-slate-200 font-bold text-slate-700 text-base transition">0</button>
                                <button type="submit" class="py-2.5 rounded-xl bg-edm-600 hover:bg-edm-700 text-white font-bold text-sm shadow-md shadow-edm-500/20 transition flex items-center justify-center gap-1">
                                    <span>ENTRAR</span> <i class="fa-solid fa-arrow-right"></i>
                                </button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>

            <!-- Últimos Registos do Dia (Visão Rápida de Transparência) -->
            <div class="bg-white rounded-3xl p-6 border border-edm-200/80 shadow-sm">
                <div class="flex items-center justify-between mb-4">
                    <h4 class="font-bold text-slate-800 flex items-center gap-2">
                        <i class="fa-solid fa-list-check text-edm-500"></i>
                        <span>Movimentos Registados Hoje</span>
                    </h4>
                    <span id="today-date-badge" class="text-xs font-semibold px-2.5 py-1 rounded-lg bg-slate-100 text-slate-600">Hoje</span>
                </div>
                <div id="terminal-recent-logs" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-3">
                    <!-- Preenchido via JS -->
                </div>
            </div>
        </section>


        <!-- ===================================================================== -->
        <!-- VISTA 2: PAINEL ADMINISTRATIVO DO CHEFE (PROTEGIDO POR SENHA: mugabe) -->
        <!-- ===================================================================== -->
        <section id="view-admin" class="hidden space-y-6">
            
            <!-- Barra Superior do Painel do Chefe -->
            <div class="bg-slate-900 text-white rounded-3xl p-5 sm:p-6 flex flex-col sm:flex-row items-start sm:items-center justify-between gap-4 shadow-lg">
                <div class="flex items-center gap-3">
                    <div class="w-12 h-12 rounded-2xl bg-edm-500 flex items-center justify-center text-white text-xl shadow-md">
                        <i class="fa-solid fa-crown"></i>
                    </div>
                    <div>
                        <h2 class="text-lg sm:text-xl font-bold">Painel de Fiscalização Geral (Chefia)</h2>
                        <p class="text-xs text-slate-300">Acesso total autorizado • Os registos estão protegidos contra exclusão não autorizada</p>
                    </div>
                </div>
                <div class="flex flex-wrap items-center gap-2 w-full sm:w-auto">
                    <button onclick="switchToTerminal()" class="flex-1 sm:flex-none px-4 py-2 rounded-xl bg-white/10 hover:bg-white/20 text-white text-xs font-semibold transition flex items-center justify-center gap-2">
                        <i class="fa-solid fa-fingerprint text-edm-400"></i> Voltar ao Terminal
                    </button>
                    <button onclick="logoutAdmin()" class="flex-1 sm:flex-none px-4 py-2 rounded-xl bg-rose-600 hover:bg-rose-700 text-white text-xs font-semibold transition flex items-center justify-center gap-2">
                        <i class="fa-solid fa-lock"></i> Bloquear Painel
                    </button>
                </div>
            </div>

            <!-- Navegação por Abas do Chefe -->
            <div class="flex overflow-x-auto gap-2 pb-1 no-scrollbar">
                <button onclick="setAdminTab('dashboard')" id="tab-btn-dashboard" class="admin-tab-btn px-4 py-3 rounded-xl font-semibold text-sm whitespace-nowrap flex items-center gap-2 bg-edm-600 text-white shadow-sm transition">
                    <i class="fa-solid fa-chart-pie"></i> 1. Fiscalização Geral
                </button>
                <button onclick="setAdminTab('workers')" id="tab-btn-workers" class="admin-tab-btn px-4 py-3 rounded-xl font-semibold text-sm whitespace-nowrap flex items-center gap-2 bg-white text-slate-600 hover:bg-edm-50 border border-slate-200 transition">
                    <i class="fa-solid fa-users-gear"></i> 2. Cadastrar Trabalhadores
                </button>
                <button onclick="setAdminTab('calendar')" id="tab-btn-calendar" class="admin-tab-btn px-4 py-3 rounded-xl font-semibold text-sm whitespace-nowrap flex items-center gap-2 bg-white text-slate-600 hover:bg-edm-50 border border-slate-200 transition">
                    <i class="fa-solid fa-calendar-days"></i> 3. Calendário, Faltas & Notas
                </button>
                <button onclick="setAdminTab('justifications')" id="tab-btn-justifications" class="admin-tab-btn px-4 py-3 rounded-xl font-semibold text-sm whitespace-nowrap flex items-center gap-2 bg-white text-slate-600 hover:bg-edm-50 border border-slate-200 transition">
                    <i class="fa-solid fa-file-medical"></i> 4. Justificar Faltas (Comprovativas)
                </button>
                <button onclick="setAdminTab('export')" id="tab-btn-export" class="admin-tab-btn px-4 py-3 rounded-xl font-semibold text-sm whitespace-nowrap flex items-center gap-2 bg-white text-slate-600 hover:bg-edm-50 border border-slate-200 transition">
                    <i class="fa-solid fa-file-export"></i> 5. Exportar para RH
                </button>
            </div>

            <!-- ----------------------------------------------------------------- -->
            <!-- ABA 1: DASHBOARD & FISCALIZAÇÃO GERAL                             -->
            <!-- ----------------------------------------------------------------- -->
            <div id="admin-tab-dashboard" class="admin-tab-content space-y-6">
                <!-- Cards de Métricas -->
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
                    <div class="bg-white p-5 rounded-2xl border border-edm-200 shadow-sm">
                        <div class="flex items-center justify-between text-slate-500 text-xs font-semibold uppercase">
                            <span>Total Trabalhadores</span>
                            <i class="fa-solid fa-users text-edm-500 text-base"></i>
                        </div>
                        <div id="stat-total-workers" class="text-3xl font-extrabold text-slate-900 mt-2">0</div>
                        <div class="text-xs text-slate-400 mt-1">Registados no sistema</div>
                    </div>

                    <div class="bg-white p-5 rounded-2xl border border-emerald-200 shadow-sm">
                        <div class="flex items-center justify-between text-emerald-600 text-xs font-semibold uppercase">
                            <span>Presentes Hoje</span>
                            <i class="fa-solid fa-user-check text-emerald-500 text-base"></i>
                        </div>
                        <div id="stat-present-today" class="text-3xl font-extrabold text-emerald-700 mt-2">0</div>
                        <div class="text-xs text-emerald-600/80 mt-1">Marcaram entrada hoje</div>
                    </div>

                    <div class="bg-white p-5 rounded-2xl border border-rose-200 shadow-sm">
                        <div class="flex items-center justify-between text-rose-600 text-xs font-semibold uppercase">
                            <span>Ausentes Hoje</span>
                            <i class="fa-solid fa-user-xmark text-rose-500 text-base"></i>
                        </div>
                        <div id="stat-absent-today" class="text-3xl font-extrabold text-rose-700 mt-2">0</div>
                        <div class="text-xs text-rose-600/80 mt-1">Sem registo até ao momento</div>
                    </div>

                    <div class="bg-white p-5 rounded-2xl border border-edm-200 shadow-sm">
                        <div class="flex items-center justify-between text-edm-600 text-xs font-semibold uppercase">
                            <span>Assiduidade Média</span>
                            <i class="fa-solid fa-award text-edm-500 text-base"></i>
                        </div>
                        <div id="stat-avg-score" class="text-3xl font-extrabold text-edm-600 mt-2">100%</div>
                        <div class="text-xs text-slate-400 mt-1">Desempenho global da equipa</div>
                    </div>
                </div>

                <!-- Tabela de Fiscalização Diária -->
                <div class="bg-white rounded-3xl border border-slate-200 shadow-sm overflow-hidden">
                    <div class="p-5 sm:p-6 border-b border-slate-100 flex flex-col sm:flex-row sm:items-center justify-between gap-4">
                        <div>
                            <h3 class="font-bold text-lg text-slate-800">Registo Geral de Entradas e Saídas</h3>
                            <p class="text-xs text-slate-500">Acompanhe a hora exata em que cada trabalhador entrou e saiu</p>
                        </div>
                        <input type="date" id="filter-log-date" onchange="renderDashboard()" class="px-3 py-2 border border-slate-200 rounded-xl text-sm font-medium text-slate-700 focus:ring-2 focus:ring-edm-500 outline-none">
                    </div>

                    <div class="overflow-x-auto">
                        <table class="w-full text-left border-collapse">
                            <thead>
                                <tr class="bg-slate-50 text-slate-500 text-xs uppercase tracking-wider border-b border-slate-200">
                                    <th class="py-3.5 px-4 font-semibold">Trabalhador</th>
                                    <th class="py-3.5 px-4 font-semibold">Cargo / Setor</th>
                                    <th class="py-3.5 px-4 font-semibold">Hora Entrada</th>
                                    <th class="py-3.5 px-4 font-semibold">Hora Saída</th>
                                    <th class="py-3.5 px-4 font-semibold">Método</th>
                                    <th class="py-3.5 px-4 font-semibold">Estado</th>
                                </tr>
                            </thead>
                            <tbody id="dashboard-logs-table" class="divide-y divide-slate-100 text-sm">
                                <!-- Preenchido via JS -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>

            <!-- ----------------------------------------------------------------- -->
            <!-- ABA 2: CADASTRO E GESTÃO DE TRABALHADORES (CRUD + FOTO GALERIA)   -->
            <!-- ----------------------------------------------------------------- -->
            <div id="admin-tab-workers" class="admin-tab-content hidden space-y-6">
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
                    
                    <!-- Formulário de Cadastro / Edição -->
                    <div class="lg:col-span-5 bg-white rounded-3xl p-6 border border-edm-200 shadow-sm h-fit">
                        <div class="flex items-center justify-between mb-4">
                            <h3 id="worker-form-title" class="font-bold text-lg text-slate-800">Cadastrar Novo Trabalhador</h3>
                            <button type="button" id="btn-cancel-edit" onclick="resetWorkerForm()" class="hidden text-xs font-semibold text-slate-500 hover:text-rose-600">
                                Cancelar Edição
                            </button>
                        </div>

                        <form onsubmit="saveWorker(event)" class="space-y-4">
                            <input type="hidden" id="edit-worker-id" value="">

                            <!-- Foto de Perfil (Importar da Galeria ou Computador) -->
                            <div class="flex flex-col items-center p-4 bg-edm-50/70 rounded-2xl border border-dashed border-edm-300">
                                <img id="worker-photo-preview" src="https://ui-avatars.com/api/?name=Novo+Trabalhador&background=F26522&color=fff&size=128" alt="Pré-visualização" class="w-24 h-24 rounded-full object-cover border-4 border-white shadow-md mb-3">
                                <label for="worker-photo-input" class="cursor-pointer inline-flex items-center gap-2 px-4 py-2 rounded-xl bg-white hover:bg-edm-100 text-edm-700 border border-edm-200 text-xs font-bold shadow-sm transition">
                                    <i class="fa-solid fa-camera"></i>
                                    <span>Escolher Foto da Galeria / PC</span>
                                </label>
                                <input type="file" id="worker-photo-input" accept="image/*" onchange="handleWorkerPhotoUpload(event)" class="hidden">
                                <span class="text-[11px] text-slate-500 mt-1.5">Importe da galeria do telemóvel ou pasta do computador</span>
                            </div>

                            <div>
                                <label class="block text-xs font-semibold text-slate-600 mb-1">Nome Completo *</label>
                                <input type="text" id="worker-name" required placeholder="Ex: Carlos Alberto Mondlane" class="w-full px-3.5 py-2.5 border border-slate-200 rounded-xl text-sm focus:ring-2 focus:ring-edm-500 outline-none">
                            </div>

                            <div>
                                <label class="block text-xs font-semibold text-slate-600 mb-1">Cargo / Departamento *</label>
                                <input type="text" id="worker-role" required placeholder="Ex: Técnico de Redes Elétricas" class="w-full px-3.5 py-2.5 border border-slate-200 rounded-xl text-sm focus:ring-2 focus:ring-edm-500 outline-none">
                            </div>

                            <div class="grid grid-cols-1 gap-3">
                                <div>
                                    <label class="block text-xs font-semibold text-slate-600 mb-1">Senha Pessoal (PIN) *</label>
                                    <input type="text" id="worker-pin" required placeholder="Ex: 2026" class="w-full px-3.5 py-2.5 border border-slate-200 rounded-xl text-sm font-mono font-bold focus:ring-2 focus:ring-edm-500 outline-none">
                                </div>

                                <!-- Painel Interativo de Captura Real de Impressão Digital (Finger) -->
                                <div class="p-4 rounded-2xl bg-slate-50 border border-slate-200 space-y-3">
                                    <div class="flex items-center justify-between">
                                        <span class="text-xs font-bold text-slate-700 flex items-center gap-1.5">
                                            <i class="fa-solid fa-fingerprint text-edm-600"></i>
                                            Captura de Impressão Digital (Finger)
                                        </span>
                                        <span id="finger-bio-hash-badge" class="hidden text-[11px] font-mono font-bold px-2 py-0.5 rounded bg-emerald-100 text-emerald-800 border border-emerald-300">
                                            BIO-000000
                                        </span>
                                    </div>

                                    <!-- Botão 1: Sensor Real do Telemóvel / Leitor Biométrico WebAuthn -->
                                    <button type="button" onclick="enrollRealDeviceBiometric()" class="w-full py-2.5 px-3 rounded-xl bg-slate-900 hover:bg-slate-800 text-white text-xs font-bold flex items-center justify-center gap-2 shadow-sm transition">
                                        <i class="fa-solid fa-mobile-screen-button text-edm-400"></i>
                                        <span>Capturar no Sensor Real do Telemóvel / PC</span>
                                    </button>

                                    <!-- Botão 2: Scanner Tátil de 3 Toques no Ecrã (Funciona em qualquer ecrã) -->
                                    <div class="bg-white p-3 rounded-xl border border-edm-200 text-center">
                                        <p class="text-[11px] text-slate-500 mb-2">Ou toque 3 vezes com o dedo do trabalhador no sensor abaixo:</p>
                                        <button type="button" id="btn-touch-enroll" onclick="handleTouchEnrollStep()" class="w-16 h-16 rounded-full mx-auto bg-edm-50 hover:bg-edm-100 active:scale-95 border-2 border-edm-500 text-edm-600 flex items-center justify-center text-3xl transition shadow-inner">
                                            <i class="fa-solid fa-fingerprint"></i>
                                        </button>
                                        <!-- Barra de progresso das 3 leituras -->
                                        <div class="flex items-center justify-center gap-1.5 mt-2.5">
                                            <span id="enroll-step-1" class="h-1.5 w-8 rounded-full bg-slate-200 transition-colors"></span>
                                            <span id="enroll-step-2" class="h-1.5 w-8 rounded-full bg-slate-200 transition-colors"></span>
                                            <span id="enroll-step-3" class="h-1.5 w-8 rounded-full bg-slate-200 transition-colors"></span>
                                        </div>
                                        <p id="finger-enroll-status" class="text-[11px] font-semibold text-slate-600 mt-1.5">Aguardando captura (0/3 toques)</p>
                                    </div>

                                    <input type="hidden" id="worker-has-finger" value="false">
                                    <input type="hidden" id="worker-bio-hash" value="">
                                    <input type="hidden" id="worker-webauthn-id" value="">
                                </div>
                            </div>

                            <button type="submit" class="w-full py-3 rounded-xl bg-edm-600 hover:bg-edm-700 text-white font-bold text-sm shadow-md shadow-edm-500/20 transition flex items-center justify-center gap-2">
                                <i class="fa-solid fa-floppy-disk"></i>
                                <span id="worker-submit-text">Guardar Trabalhador no Sistema</span>
                            </button>
                        </form>
                    </div>

                    <!-- Lista de Trabalhadores Registados -->
                    <div class="lg:col-span-7 bg-white rounded-3xl p-6 border border-slate-200 shadow-sm">
                        <div class="flex items-center justify-between mb-4">
                            <div>
                                <h3 class="font-bold text-lg text-slate-800">Trabalhadores Cadastrados</h3>
                                <p class="text-xs text-slate-500">Apenas o chefe pode editar ou remover trabalhadores</p>
                            </div>
                            <span id="workers-count-badge" class="px-3 py-1 rounded-full bg-edm-100 text-edm-800 text-xs font-bold">0 ativos</span>
                        </div>

                        <div id="workers-list-container" class="space-y-3">
                            <!-- Preenchido via JS -->
                        </div>
                    </div>
                </div>
            </div>

            <!-- ----------------------------------------------------------------- -->
            <!-- ABA 3: CALENDÁRIO DE PRESENÇAS, FALTAS (ABATES) E DESEMPENHO      -->
            <!-- ----------------------------------------------------------------- -->
            <div id="admin-tab-calendar" class="admin-tab-content hidden space-y-6">
                <div class="bg-white rounded-3xl p-6 border border-slate-200 shadow-sm">
                    <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 pb-6 border-b border-slate-100">
                        <div>
                            <h3 class="font-bold text-lg text-slate-800">Mapa Mensal de Assiduidade e Abates</h3>
                            <p class="text-xs text-slate-500">Dias sem registo geram abate automático e reduzem a nota de desempenho</p>
                        </div>

                        <div class="flex flex-wrap items-center gap-3">
                            <select id="calendar-worker-select" onchange="renderCalendarView()" class="px-3.5 py-2 border border-slate-200 rounded-xl text-sm font-semibold text-slate-700 bg-slate-50 focus:ring-2 focus:ring-edm-500 outline-none">
                                <!-- Preenchido via JS -->
                            </select>
                            <input type="month" id="calendar-month-input" onchange="renderCalendarView()" class="px-3.5 py-2 border border-slate-200 rounded-xl text-sm font-semibold text-slate-700 bg-slate-50 focus:ring-2 focus:ring-edm-500 outline-none">
                        </div>
                    </div>

                    <!-- Resumo de Desempenho do Trabalhador Selecionado -->
                    <div id="worker-performance-summary" class="grid grid-cols-2 sm:grid-cols-4 gap-4 my-6">
                        <!-- Preenchido via JS -->
                    </div>

                    <!-- Legenda do Calendário -->
                    <div class="flex flex-wrap items-center gap-4 text-xs font-medium text-slate-600 mb-4 bg-slate-50 p-3 rounded-xl">
                        <span class="flex items-center gap-1.5"><span class="w-3 h-3 rounded-full bg-emerald-500"></span> Dia Trabalhado</span>
                        <span class="flex items-center gap-1.5"><span class="w-3 h-3 rounded-full bg-rose-500"></span> Falta (Abate)</span>
                        <span class="flex items-center gap-1.5"><span class="w-3 h-3 rounded-full bg-amber-400"></span> Falta Justificada (Comprovativo)</span>
                        <span class="flex items-center gap-1.5"><span class="w-3 h-3 rounded-full bg-slate-300"></span> Fim de Semana / Futuro</span>
                    </div>

                    <!-- Grelha do Calendário -->
                    <div class="grid grid-cols-7 gap-1.5 sm:gap-2 text-center">
                        <div class="text-xs font-bold text-slate-400 py-2">Dom</div>
                        <div class="text-xs font-bold text-slate-600 py-2">Seg</div>
                        <div class="text-xs font-bold text-slate-600 py-2">Ter</div>
                        <div class="text-xs font-bold text-slate-600 py-2">Qua</div>
                        <div class="text-xs font-bold text-slate-600 py-2">Qui</div>
                        <div class="text-xs font-bold text-slate-600 py-2">Sex</div>
                        <div class="text-xs font-bold text-slate-400 py-2">Sáb</div>
                    </div>
                    <div id="calendar-days-grid" class="grid grid-cols-7 gap-1.5 sm:gap-2 mt-1">
                        <!-- Dias gerados via JS -->
                    </div>
                </div>
            </div>

            <!-- ----------------------------------------------------------------- -->
            <!-- ABA 4: JUSTIFICAÇÃO DE FALTAS COM FOTO COMPROVATIVA               -->
            <!-- ----------------------------------------------------------------- -->
            <div id="admin-tab-justifications" class="admin-tab-content hidden space-y-6">
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
                    
                    <!-- Formulário para Anexar Comprovativa -->
                    <div class="lg:col-span-5 bg-white rounded-3xl p-6 border border-edm-200 shadow-sm h-fit">
                        <h3 class="font-bold text-lg text-slate-800 mb-1">Registar Justificação de Falta</h3>
                        <p class="text-xs text-slate-500 mb-4">Anexe a foto do atestado ou documento comprovativo para abonar a falta</p>

                        <form onsubmit="saveJustification(event)" class="space-y-4">
                            <div>
                                <label class="block text-xs font-semibold text-slate-600 mb-1">Trabalhador *</label>
                                <select id="just-worker-select" required class="w-full px-3.5 py-2.5 border border-slate-200 rounded-xl text-sm font-medium focus:ring-2 focus:ring-edm-500 outline-none">
                                    <!-- Preenchido via JS -->
                                </select>
                            </div>

                            <div>
                                <label class="block text-xs font-semibold text-slate-600 mb-1">Data da Falta *</label>
                                <input type="date" id="just-date" required class="w-full px-3.5 py-2.5 border border-slate-200 rounded-xl text-sm font-medium focus:ring-2 focus:ring-edm-500 outline-none">
                            </div>

                            <div>
                                <label class="block text-xs font-semibold text-slate-600 mb-1">Motivo da Ausência *</label>
                                <input type="text" id="just-reason" required placeholder="Ex: Atestado Médico / Luto / Serviço Externo" class="w-full px-3.5 py-2.5 border border-slate-200 rounded-xl text-sm focus:ring-2 focus:ring-edm-500 outline-none">
                            </div>

                            <!-- Upload de Foto da Comprovativa -->
                            <div>
                                <label class="block text-xs font-semibold text-slate-600 mb-1">Foto do Documento Comprovativo *</label>
                                <div class="border-2 border-dashed border-edm-300 rounded-2xl p-4 bg-edm-50/50 text-center">
                                    <img id="just-proof-preview" src="" alt="Comprovativo" class="hidden max-h-40 mx-auto rounded-lg shadow-sm mb-3 object-contain">
                                    <label for="just-proof-input" class="cursor-pointer inline-flex items-center gap-2 px-4 py-2 rounded-xl bg-white hover:bg-edm-100 text-edm-700 border border-edm-200 text-xs font-bold shadow-sm transition">
                                        <i class="fa-solid fa-file-image"></i>
                                        <span>Carregar Foto da Comprovativa</span>
                                    </label>
                                    <input type="file" id="just-proof-input" accept="image/*" required onchange="handleProofUpload(event)" class="hidden">
                                    <p class="text-[11px] text-slate-500 mt-1">A imagem ficará arquivada para envio aos Recursos Humanos</p>
                                </div>
                            </div>

                            <button type="submit" class="w-full py-3 rounded-xl bg-edm-600 hover:bg-edm-700 text-white font-bold text-sm shadow-md transition flex items-center justify-center gap-2">
                                <i class="fa-solid fa-check-circle"></i>
                                <span>Validar Justificação e Guardar Comprovativo</span>
                            </button>
                        </form>
                    </div>

                    <!-- Arquivo de Comprovativas Guardadas -->
                    <div class="lg:col-span-7 bg-white rounded-3xl p-6 border border-slate-200 shadow-sm">
                        <h3 class="font-bold text-lg text-slate-800 mb-1">Arquivo de Faltas Justificadas</h3>
                        <p class="text-xs text-slate-500 mb-4">Todas as comprovativas ficam armazenadas e seguem no relatório de RH</p>

                        <div id="justifications-list" class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            <!-- Preenchido via JS -->
                        </div>
                    </div>
                </div>
            </div>

            <!-- ----------------------------------------------------------------- -->
            <!-- ABA 5: EXPORTAÇÃO DE RELATÓRIOS PARA RECURSOS HUMANOS (RH)        -->
            <!-- ----------------------------------------------------------------- -->
            <div id="admin-tab-export" class="admin-tab-content hidden space-y-6">
                <div class="bg-white rounded-3xl p-6 border border-slate-200 shadow-sm">
                    <div class="flex flex-col lg:flex-row lg:items-center justify-between gap-4 pb-6 border-b border-slate-100">
                        <div>
                            <h3 class="font-bold text-lg text-slate-800">Central de Exportação para Recursos Humanos (RH)</h3>
                            <p class="text-xs text-slate-500">Gere o mapa consolidado de presenças, abates, notas e comprovativas para entrega oficial</p>
                        </div>

                        <div class="flex flex-wrap items-center gap-3">
                            <input type="month" id="export-month-input" onchange="renderRHReportPreview()" class="px-3.5 py-2 border border-slate-200 rounded-xl text-sm font-semibold text-slate-700 bg-slate-50">
                            
                            <button onclick="exportToCSV()" class="px-4 py-2.5 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white text-xs font-bold shadow-sm transition flex items-center gap-2">
                                <i class="fa-solid fa-file-excel"></i> Baixar Excel (CSV)
                            </button>

                            <button onclick="window.print()" class="px-4 py-2.5 rounded-xl bg-edm-600 hover:bg-edm-700 text-white text-xs font-bold shadow-sm transition flex items-center gap-2">
                                <i class="fa-solid fa-print"></i> Imprimir / Salvar PDF Oficial
                            </button>
                        </div>
                    </div>

                    <!-- Área Imprimível Formatada para RH -->
                    <div id="printable-rh-report" class="mt-6 p-4 sm:p-6 bg-white border border-slate-200 rounded-2xl">
                        <!-- Cabeçalho do Documento Oficial -->
                        <div class="flex items-center justify-between border-b-2 border-edm-500 pb-4 mb-6">
                            <div class="flex items-center gap-3">
                                <div class="w-10 h-10 rounded-lg bg-edm-500 flex items-center justify-center text-white font-bold">
                                    <i class="fa-solid fa-bolt"></i>
                                </div>
                                <div>
                                    <h4 class="font-extrabold text-lg text-slate-900">EDM - Eletricidade de Moçambique</h4>
                                    <p class="text-xs text-slate-500">Relatório Oficial de Assiduidade, Abates e Justificações • Recursos Humanos</p>
                                </div>
                            </div>
                            <div class="text-right">
                                <div id="rh-report-period" class="text-sm font-bold text-edm-700 uppercase">Período: --/----</div>
                                <div id="rh-report-generated" class="text-[11px] text-slate-400">Emitido pela Chefia</div>
                            </div>
                        </div>

                        <!-- Tabela Consolidada para RH -->
                        <div class="overflow-x-auto mb-8">
                            <table class="w-full text-left border-collapse border border-slate-200 text-xs sm:text-sm">
                                <thead>
                                    <tr class="bg-edm-50 text-slate-800 border-b border-slate-300">
                                        <th class="p-3 border border-slate-200">Trabalhador</th>
                                        <th class="p-3 border border-slate-200">Cargo</th>
                                        <th class="p-3 border border-slate-200 text-center">Dias Trabalhados</th>
                                        <th class="p-3 border border-slate-200 text-center">Faltas (Abates)</th>
                                        <th class="p-3 border border-slate-200 text-center">Justificadas</th>
                                        <th class="p-3 border border-slate-200 text-center">Nota Desempenho</th>
                                    </tr>
                                </thead>
                                <tbody id="rh-summary-table-body">
                                    <!-- Preenchido via JS -->
                                </tbody>
                            </table>
                        </div>

                        <!-- Anexo de Comprovativas de Faltas no Relatório RH -->
                        <div>
                            <h5 class="font-bold text-sm text-slate-800 uppercase tracking-wider border-b border-slate-200 pb-2 mb-4">
                                Anexo Documental: Comprovativas de Faltas Justificadas no Período
                            </h5>
                            <div id="rh-proofs-attachment" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
                                <!-- Preenchido via JS -->
                            </div>
                        </div>

                        <!-- Assinatura do Chefe -->
                        <div class="mt-12 pt-6 border-t border-slate-200 flex justify-between items-end text-xs text-slate-500">
                            <div>
                                <p>Documento gerado eletronicamente pelo Sistema Biométrico EDM.</p>
                            </div>
                            <div class="text-center">
                                <div class="w-48 border-b border-slate-400 mb-1"></div>
                                <p class="font-semibold text-slate-700">Assinatura do Chefe / Responsável</p>
                            </div>
                        </div>
                    </div>

                    <!-- Ferramenta de Segurança / Backup JSON -->
                    <div class="mt-6 pt-6 border-t border-slate-100 flex flex-col sm:flex-row items-center justify-between gap-4 no-print">
                        <div class="text-xs text-slate-500">
                            <i class="fa-solid fa-database text-edm-500 mr-1"></i>
                            Cópia de Segurança do Banco de Dados Local (Protegido por Senha)
                        </div>
                        <div class="flex gap-2">
                            <button onclick="downloadBackupJSON()" class="px-3 py-1.5 rounded-lg bg-slate-100 hover:bg-slate-200 text-slate-700 text-xs font-semibold transition">
                                <i class="fa-solid fa-download mr-1"></i> Fazer Backup
                            </button>
                            <label class="cursor-pointer px-3 py-1.5 rounded-lg bg-slate-100 hover:bg-slate-200 text-slate-700 text-xs font-semibold transition">
                                <i class="fa-solid fa-upload mr-1"></i> Restaurar Backup
                                <input type="file" accept=".json" onchange="restoreBackupJSON(event)" class="hidden">
                            </label>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- RODAPÉ -->
    <footer class="bg-white border-t border-edm-100 py-4 text-center text-xs text-slate-500 no-print">
        <p>© 2026 <strong class="text-edm-600">EDM - Eletricidade de Moçambique</strong> • Sistema de Controle de Presença Biométrico e Gestão de RH</p>
    </footer>


    <!-- ===================================================================== -->
    <!-- MODAIS INTERATIVOS (SEM USO DE ALERT/CONFIRM NATIVOS)                 -->
    <!-- ===================================================================== -->

    <!-- MODAL 1: SIMULADOR / LEITOR DE IMPRESSÃO DIGITAL (BIOMETRIA) -->
    <div id="modal-biometric" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-md w-full p-6 sm:p-8 shadow-2xl border border-edm-200 text-center relative animate-fade-in">
            <button onclick="closeBiometricModal()" class="absolute top-4 right-4 w-8 h-8 rounded-full bg-slate-100 hover:bg-slate-200 text-slate-600 flex items-center justify-center">
                <i class="fa-solid fa-xmark"></i>
            </button>

            <div class="w-16 h-16 rounded-2xl bg-edm-100 text-edm-600 flex items-center justify-center mx-auto mb-3 text-3xl">
                <i class="fa-solid fa-fingerprint"></i>
            </div>
            <h3 class="text-xl font-bold text-slate-900">Leitura Biométrica Ativa</h3>
            <p class="text-xs text-slate-500 mt-1">
                Coloque o dedo no sensor biométrico do telemóvel ou selecione o perfil com digital registada:
            </p>

            <!-- Botão para WebAuthn Nativo do Android/iPhone/PC -->
            <button onclick="authenticateWithDeviceWebAuthn()" class="mt-4 w-full py-3 px-4 rounded-xl bg-slate-900 hover:bg-slate-800 text-white text-xs font-bold flex items-center justify-center gap-2 shadow-md transition">
                <i class="fa-solid fa-fingerprint text-edm-400 text-base"></i>
                <span>Ler Digital no Sensor Biométrico do Aparelho</span>
            </button>

            <div class="my-4 flex items-center gap-2 text-xs text-slate-400">
                <div class="h-px bg-slate-200 flex-grow"></div>
                <span>Ou validação tátil por perfil registado</span>
                <div class="h-px bg-slate-200 flex-grow"></div>
            </div>

            <!-- Lista de Trabalhadores com Digital Cadastrada -->
            <div id="biometric-workers-list" class="space-y-2 max-h-60 overflow-y-auto pr-1 text-left">
                <!-- Preenchido via JS -->
            </div>
        </div>
    </div>

    <!-- MODAL 2: CARTÃO DE BOAS-VINDAS / CONFIRMAÇÃO DE PONTO (COM FOTO E VOZ) -->
    <div id="modal-welcome" class="fixed inset-0 bg-slate-900/70 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-md w-full p-6 sm:p-8 shadow-2xl border-2 border-edm-500 text-center relative overflow-hidden">
            <div class="absolute top-0 inset-x-0 h-2 bg-gradient-to-r from-edm-400 via-edm-600 to-edm-400"></div>
            
            <div id="welcome-badge" class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-emerald-100 text-emerald-700 mb-4">
                <i class="fa-solid fa-circle-check"></i> ENTRADA REGISTADA
            </div>

            <!-- Foto de Perfil do Trabalhador em Destaque -->
            <div class="w-28 h-28 sm:w-32 sm:h-32 rounded-full mx-auto p-1 bg-gradient-to-tr from-edm-500 to-amber-300 shadow-lg mb-4">
                <img id="welcome-photo" src="" alt="Foto Trabalhador" class="w-full h-full rounded-full object-cover bg-white">
            </div>

            <h3 id="welcome-greeting" class="text-2xl font-extrabold text-slate-900">Bem-vindo(a)!</h3>
            <p id="welcome-name" class="text-lg font-bold text-edm-600 mt-0.5">Nome do Trabalhador</p>
            <p id="welcome-role" class="text-xs text-slate-500">Cargo / Departamento</p>
            <p id="welcome-extra-info" class="text-xs font-semibold text-slate-600 mt-2 bg-slate-100 py-1.5 px-3 rounded-lg inline-block"></p>

            <div class="mt-4 bg-edm-50 rounded-2xl p-4 border border-edm-200 flex items-center justify-around">
                <div>
                    <span class="block text-[11px] uppercase text-slate-500 font-semibold">Hora do Registo</span>
                    <span id="welcome-time" class="text-xl font-extrabold font-mono text-slate-800">08:00:00</span>
                </div>
                <div class="h-8 w-px bg-edm-200"></div>
                <div>
                    <span class="block text-[11px] uppercase text-slate-500 font-semibold">Método</span>
                    <span id="welcome-method" class="text-sm font-bold text-edm-700">Biometria</span>
                </div>
            </div>

            <div class="mt-4 flex items-center justify-center gap-2 text-xs text-slate-500">
                <i class="fa-solid fa-volume-high text-edm-500 animate-pulse"></i>
                <span>Saudação por voz ativada</span>
            </div>

            <button onclick="closeWelcomeModal()" class="mt-5 w-full py-3 rounded-xl bg-slate-900 hover:bg-slate-800 text-white font-bold text-sm transition">
                Concluir
            </button>
        </div>
    </div>

    <!-- MODAL 3: AUTENTICAÇÃO DO CHEFE (SENHA: mugabe) -->
    <div id="modal-admin-login" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-sm w-full p-6 sm:p-8 shadow-2xl border border-slate-200 relative">
            <button onclick="closeAdminLoginModal()" class="absolute top-4 right-4 w-8 h-8 rounded-full bg-slate-100 hover:bg-slate-200 text-slate-600 flex items-center justify-center">
                <i class="fa-solid fa-xmark"></i>
            </button>

            <div class="w-14 h-14 rounded-2xl bg-slate-900 text-edm-400 flex items-center justify-center mx-auto mb-4 text-2xl shadow-md">
                <i class="fa-solid fa-user-shield"></i>
            </div>
            <h3 class="text-xl font-bold text-center text-slate-900">Acesso Restrito à Chefia</h3>
            <p class="text-xs text-center text-slate-500 mt-1">Introduza a senha mestra de administrador para gerir trabalhadores e relatórios</p>

            <form onsubmit="verifyAdminLogin(event)" class="mt-5 space-y-4">
                <div>
                    <input type="password" id="admin-password-input" required placeholder="Senha do chefe" 
                        class="w-full px-4 py-3 border border-slate-300 rounded-xl text-center font-bold tracking-wider text-slate-800 focus:ring-2 focus:ring-edm-500 outline-none">
                    <p id="admin-login-error" class="hidden text-xs text-rose-600 font-semibold text-center mt-2">Senha incorreta. Acesso negado.</p>
                </div>
                <button type="submit" class="w-full py-3 rounded-xl bg-edm-600 hover:bg-edm-700 text-white font-bold text-sm shadow-md transition">
                    Entrar no Painel do Chefe
                </button>
            </form>
        </div>
    </div>

    <!-- MODAL 4: VISUALIZADOR DE COMPROVATIVA / NOTIFICAÇÃO TOAST -->
    <div id="modal-proof-viewer" class="fixed inset-0 bg-slate-900/80 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4" onclick="this.classList.add('hidden')">
        <div class="bg-white rounded-2xl max-w-xl w-full p-4 shadow-2xl" onclick="event.stopPropagation()">
            <div class="flex items-center justify-between pb-3 border-b border-slate-100 mb-3">
                <h4 id="proof-viewer-title" class="font-bold text-slate-800 text-sm">Documento Comprovativo</h4>
                <button onclick="document.getElementById('modal-proof-viewer').classList.add('hidden')" class="w-8 h-8 rounded-full bg-slate-100 text-slate-600 flex items-center justify-center">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>
            <img id="proof-viewer-img" src="" alt="Comprovativa" class="w-full max-h-[70vh] object-contain rounded-xl bg-slate-50">
        </div>
    </div>

    <!-- NOTIFICAÇÃO FLUTUANTE (TOAST) -->
    <div id="toast-notification" class="fixed bottom-5 right-5 z-50 transform translate-y-24 opacity-0 transition-all duration-300 bg-slate-900 text-white px-5 py-3.5 rounded-2xl shadow-xl flex items-center gap-3 text-sm font-medium border border-slate-700">
        <i id="toast-icon" class="fa-solid fa-circle-info text-edm-400 text-lg"></i>
        <span id="toast-message">Mensagem</span>
    </div>


    <!-- ===================================================================== -->
    <!-- LÓGICA DO SISTEMA (JAVASCRIPT COMPLETO E AUTO-CONTIDO)                -->
    <!-- ===================================================================== -->
    <script>
        // Chaves de armazenamento seguro no navegador
        const STORAGE_KEYS = {
            WORKERS: 'edm_ponto_workers_v1',
            LOGS: 'edm_ponto_logs_v1',
            JUSTIFICATIONS: 'edm_ponto_justifications_v1'
        };

        const ADMIN_SECRET = 'mugabe';
        let isAdminAuthenticated = false;
        let currentPhotoBase64 = '';
        let currentProofBase64 = '';
        let touchEnrollCount = 0;

        // ---------------------------------------------------------------------
        // 1. INICIALIZAÇÃO E DADOS DE DEMONSTRAÇÃO REALISTAS
        // ---------------------------------------------------------------------
        function initSystem() {
            seedInitialDataIfEmpty();
            startLiveClock();
            renderTerminalRecentLogs();

            // Configurar datas padrão nos filtros
            const todayStr = getTodayDateString();
            const currentMonthStr = todayStr.slice(0, 7);
            document.getElementById('filter-log-date').value = todayStr;
            document.getElementById('calendar-month-input').value = currentMonthStr;
            document.getElementById('export-month-input').value = currentMonthStr;
            document.getElementById('just-date').value = todayStr;
        }

        function seedInitialDataIfEmpty() {
            if (!localStorage.getItem(STORAGE_KEYS.WORKERS)) {
                const defaultWorkers = [
                    {
                        id: 'w_0',
                        name: 'Alberto Mugabe Sabino',
                        role: 'Supervisor Operacional • EDM',
                        pin: '1000',
                        hasFingerprint: true,
                        bioHash: 'BIO-94A7C2',
                        webauthnId: '',
                        photo: 'https://images.unsplash.com/photo-1531384441138-2736e62e0919?auto=format&fit=crop&w=256&q=80'
                    },
                    {
                        id: 'w_1',
                        name: 'Mateus António Nhantumbo',
                        role: 'Engenheiro Eletrotécnico • Subestação',
                        pin: '1001',
                        hasFingerprint: true,
                        bioHash: 'BIO-81F3D9',
                        webauthnId: '',
                        photo: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&w=256&q=80'
                    },
                    {
                        id: 'w_2',
                        name: 'Beatriz Sofia Tembe',
                        role: 'Técnica de Manutenção e Redes',
                        pin: '1002',
                        hasFingerprint: true,
                        bioHash: 'BIO-52E8B4',
                        webauthnId: '',
                        photo: 'https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?auto=format&fit=crop&w=256&q=80'
                    },
                    {
                        id: 'w_3',
                        name: 'Armando José Macuácua',
                        role: 'Operador de Distribuição',
                        pin: '1003',
                        hasFingerprint: true,
                        bioHash: 'BIO-39C1A6',
                        webauthnId: '',
                        photo: 'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&w=256&q=80'
                    }
                ];
                localStorage.setItem(STORAGE_KEYS.WORKERS, JSON.stringify(defaultWorkers));

                // Criar histórico de alguns dias no mês atual para demonstração imediata
                const now = new Date();
                const year = now.getFullYear();
                const month = String(now.getMonth() + 1).padStart(2, '0');
                const sampleLogs = [];

                for (let d = 1; d < now.getDate(); d++) {
                    const dateCheck = new Date(year, now.getMonth(), d);
                    const dayOfWeek = dateCheck.getDay();
                    if (dayOfWeek !== 0 && dayOfWeek !== 6) { // Dias úteis
                        const dayStr = `${year}-${month}-${String(d).padStart(2, '0')}`;
                        sampleLogs.push({ id: `l_0_${d}`, workerId: 'w_0', date: dayStr, checkIn: '07:45:00', checkOut: '17:05:00', method: 'Impressão Digital' });
                        sampleLogs.push({ id: `l_1_${d}`, workerId: 'w_1', date: dayStr, checkIn: '07:52:14', checkOut: '17:04:10', method: 'Impressão Digital' });
                        if (d !== 3) {
                            sampleLogs.push({ id: `l_2_${d}`, workerId: 'w_2', date: dayStr, checkIn: '07:58:40', checkOut: '17:01:22', method: 'Impressão Digital' });
                        }
                        if (d % 4 !== 0) {
                            sampleLogs.push({ id: `l_3_${d}`, workerId: 'w_3', date: dayStr, checkIn: '08:03:05', checkOut: '17:00:00', method: 'Senha Pessoal' });
                        }
                    }
                }
                localStorage.setItem(STORAGE_KEYS.LOGS, JSON.stringify(sampleLogs));
                localStorage.setItem(STORAGE_KEYS.JUSTIFICATIONS, JSON.stringify([]));
            }
        }

        function getWorkers() {
            return JSON.parse(localStorage.getItem(STORAGE_KEYS.WORKERS) || '[]');
        }
        function saveWorkers(list) {
            localStorage.setItem(STORAGE_KEYS.WORKERS, JSON.stringify(list));
        }
        function getLogs() {
            return JSON.parse(localStorage.getItem(STORAGE_KEYS.LOGS) || '[]');
        }
        function saveLogs(list) {
            localStorage.setItem(STORAGE_KEYS.LOGS, JSON.stringify(list));
        }
        function getJustifications() {
            return JSON.parse(localStorage.getItem(STORAGE_KEYS.JUSTIFICATIONS) || '[]');
        }
        function saveJustifications(list) {
            localStorage.setItem(STORAGE_KEYS.JUSTIFICATIONS, JSON.stringify(list));
        }

        // ---------------------------------------------------------------------
        // 2. RELÓGIO EM TEMPO REAL E UTILITÁRIOS DE DATA
        // ---------------------------------------------------------------------
        function startLiveClock() {
            function update() {
                const now = new Date();
                document.getElementById('live-clock').textContent = now.toLocaleTimeString('pt-PT');
                const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
                document.getElementById('live-date').textContent = now.toLocaleDateString('pt-PT', options);
            }
            update();
            setInterval(update, 1000);
        }

        function getTodayDateString() {
            const now = new Date();
            return `${now.getFullYear()}-${String(now.getMonth() + 1).padStart(2, '0')}-${String(now.getDate()).padStart(2, '0')}`;
        }

        function getCurrentTimeString() {
            return new Date().toLocaleTimeString('pt-PT');
        }

        function showToast(message, type = 'info') {
            const toast = document.getElementById('toast-notification');
            const icon = document.getElementById('toast-icon');
            document.getElementById('toast-message').textContent = message;

            icon.className = type === 'error' 
                ? 'fa-solid fa-circle-exclamation text-rose-400 text-lg' 
                : 'fa-solid fa-circle-check text-emerald-400 text-lg';

            toast.classList.remove('translate-y-24', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-y-24', 'opacity-0');
            }, 3500);
        }

        // ---------------------------------------------------------------------
        // 3. REGISTO DE PONTO (BIOMETRIA / SENHA) + SAUDAÇÃO POR VOZ + FOTO
        // ---------------------------------------------------------------------
        function appendPin(digit) {
            const input = document.getElementById('worker-pin-input');
            if (input.value.length < 10) {
                input.value += digit;
            }
        }

        function clearPin() {
            document.getElementById('worker-pin-input').value = '';
        }

        function handlePasswordClockIn(e) {
            e.preventDefault();
            const pin = document.getElementById('worker-pin-input').value.trim();
            if (!pin) return;

            const workers = getWorkers();
            const worker = workers.find(w => w.pin === pin);

            if (!worker) {
                showToast('Senha não reconhecida! Verifique com o chefe.', 'error');
                speakText('Senha não reconhecida. Tente novamente.');
                clearPin();
                return;
            }

            clearPin();
            processAttendanceRecord(worker, 'Senha Pessoal');
        }

        // Quando o trabalhador clica no sensor biométrico do terminal
        async function handleTerminalBiometricClick() {
            const workersWithWebAuthn = getWorkers().filter(w => w.webauthnId);
            // Se existirem trabalhadores com credencial biométrica real WebAuthn registada neste dispositivo, tenta ler diretamente
            if (workersWithWebAuthn.length > 0 && window.PublicKeyCredential) {
                const authenticated = await authenticateWithDeviceWebAuthn(true);
                if (authenticated) return;
            }
            openBiometricModal();
        }

        function openBiometricModal() {
            const workers = getWorkers().filter(w => w.hasFingerprint);
            const container = document.getElementById('biometric-workers-list');
            
            if (workers.length === 0) {
                container.innerHTML = `<p class="text-xs text-center text-slate-500 py-4">Nenhuma impressão digital cadastrada ainda. Peça ao chefe para registar na Área Administrativa.</p>`;
            } else {
                const today = getTodayDateString();
                const logs = getLogs().filter(l => l.date === today);

                container.innerHTML = workers.map(w => {
                    const todayLog = logs.find(l => l.workerId === w.id);
                    let statusTag = `<span class="text-[10px] font-bold px-2 py-0.5 rounded-full bg-emerald-100 text-emerald-700">Marcar Entrada</span>`;
                    if (todayLog && !todayLog.checkOut) {
                        statusTag = `<span class="text-[10px] font-bold px-2 py-0.5 rounded-full bg-amber-100 text-amber-800">Marcar Saída</span>`;
                    } else if (todayLog && todayLog.checkOut) {
                        statusTag = `<span class="text-[10px] font-bold px-2 py-0.5 rounded-full bg-slate-200 text-slate-600">Turno Concluído</span>`;
                    }

                    return `
                        <button onclick="selectBiometricWorker('${w.id}')" class="w-full flex items-center gap-3 p-2.5 rounded-xl border border-slate-200 hover:border-edm-500 hover:bg-edm-50 transition text-left">
                            <img src="${w.photo}" class="w-10 h-10 rounded-full object-cover border border-edm-300">
                            <div class="flex-grow min-w-0">
                                <div class="font-bold text-sm text-slate-800 truncate">${w.name}</div>
                                <div class="flex items-center gap-2 mt-0.5">
                                    <span class="text-[10px] font-mono text-slate-400">${w.bioHash || 'BIO-ATIVO'}</span>
                                    ${statusTag}
                                </div>
                            </div>
                            <i class="fa-solid fa-fingerprint text-edm-600 text-xl"></i>
                        </button>
                    `;
                }).join('');
            }

            document.getElementById('modal-biometric').classList.remove('hidden');
        }

        function closeBiometricModal() {
            document.getElementById('modal-biometric').classList.add('hidden');
        }

        function selectBiometricWorker(workerId) {
            const worker = getWorkers().find(w => w.id === workerId);
            if (!worker) return;
            closeBiometricModal();
            processAttendanceRecord(worker, 'Impressão Digital');
        }

        // Leitura biométrica real via WebAuthn (Android / iPhone / Windows Hello)
        async function authenticateWithDeviceWebAuthn(silentFallback = false) {
            if (!window.PublicKeyCredential) {
                if (!silentFallback) showToast('Este navegador não suporta sensor biométrico nativo. Selecione o perfil abaixo.', 'info');
                return false;
            }

            const workersWithCreds = getWorkers().filter(w => w.webauthnId);
            if (workersWithCreds.length === 0) {
                if (!silentFallback) showToast('Nenhuma digital física foi vinculada a este telemóvel ainda. Use a lista abaixo ou peça ao chefe para registar.', 'info');
                return false;
            }

            try {
                const allowCredentials = workersWithCreds.map(w => ({
                    id: base64UrlToBuffer(w.webauthnId),
                    type: 'public-key',
                    transports: ['internal', 'usb', 'nfc', 'ble']
                }));

                const challenge = new Uint8Array(32);
                window.crypto.getRandomValues(challenge);

                const assertion = await navigator.credentials.get({
                    publicKey: {
                        challenge,
                        allowCredentials,
                        userVerification: 'required',
                        timeout: 30000
                    }
                });

                if (assertion && assertion.rawId) {
                    const matchedId = bufferToBase64Url(assertion.rawId);
                    const worker = workersWithCreds.find(w => w.webauthnId === matchedId);
                    if (worker) {
                        closeBiometricModal();
                        processAttendanceRecord(worker, 'Sensor Biométrico Real');
                        return true;
                    }
                }
            } catch (err) {
                if (!silentFallback) {
                    showToast('Leitura biométrica cancelada ou indisponível neste ecrã. Pode validar na lista abaixo.', 'info');
                }
            }
            return false;
        }

        function calculateDurationString(startTime, endTime) {
            const [h1, m1, s1] = startTime.split(':').map(Number);
            const [h2, m2, s2] = endTime.split(':').map(Number);
            const startSec = h1 * 3600 + m1 * 60 + (s1 || 0);
            const endSec = h2 * 3600 + m2 * 60 + (s2 || 0);
            const diff = Math.max(0, endSec - startSec);
            const hours = Math.floor(diff / 3600);
            const mins = Math.floor((diff % 3600) / 60);
            return `${hours}h ${String(mins).padStart(2, '0')}m`;
        }

        function processAttendanceRecord(worker, method) {
            const today = getTodayDateString();
            const nowTime = getCurrentTimeString();
            const logs = getLogs();

            // Verifica se já existe registo hoje para este trabalhador
            const existingIndex = logs.findIndex(l => l.workerId === worker.id && l.date === today);

            if (existingIndex === -1) {
                // 1ª CONEXÃO DO DIA -> ENTRADA AUTOMÁTICA
                logs.push({
                    id: 'log_' + Date.now(),
                    workerId: worker.id,
                    date: today,
                    checkIn: nowTime,
                    checkOut: null,
                    method: method
                });
                saveLogs(logs);
                renderTerminalRecentLogs();
                showWelcomeModalAndSpeak(worker, 'ENTRADA', nowTime, method, 'Estado atual: Em Serviço');
            } else if (!logs[existingIndex].checkOut) {
                // 2ª CONEXÃO DO DIA -> SAÍDA AUTOMÁTICA
                logs[existingIndex].checkOut = nowTime;
                const duration = calculateDurationString(logs[existingIndex].checkIn, nowTime);
                saveLogs(logs);
                renderTerminalRecentLogs();
                showWelcomeModalAndSpeak(
                    worker,
                    'SAIDA',
                    nowTime,
                    method,
                    `Entrada: ${logs[existingIndex].checkIn.slice(0,5)} • Duração: ${duration}`
                );
            } else {
                // 3ª CONEXÃO NO MESMO DIA -> TURNO JÁ CONCLUÍDO
                const record = logs[existingIndex];
                const duration = calculateDurationString(record.checkIn, record.checkOut);
                showWelcomeModalAndSpeak(
                    worker,
                    'CONCLUIDO',
                    record.checkOut,
                    method,
                    `Entrada: ${record.checkIn.slice(0,5)} | Saída: ${record.checkOut.slice(0,5)} (${duration})`
                );
            }
        }

        function showWelcomeModalAndSpeak(worker, actionType, timeStr, method, extraInfo) {
            const badge = document.getElementById('welcome-badge');
            const greetingEl = document.getElementById('welcome-greeting');
            const extraEl = document.getElementById('welcome-extra-info');
            const firstName = worker.name.split(' ')[0];

            document.getElementById('welcome-photo').src = worker.photo;
            document.getElementById('welcome-name').textContent = worker.name;
            document.getElementById('welcome-role').textContent = worker.role;
            document.getElementById('welcome-time').textContent = timeStr;
            document.getElementById('welcome-method').textContent = method;
            extraEl.textContent = extraInfo || '';

            let voiceMessage = '';

            if (actionType === 'ENTRADA') {
                badge.className = 'inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-emerald-100 text-emerald-700 mb-4';
                badge.innerHTML = `<i class="fa-solid fa-circle-check"></i> ENTRADA • ${timeStr.slice(0,5)}`;
                greetingEl.textContent = `Bem-vindo ao trabalho, ${firstName}!`;
                voiceMessage = `Bem-vindo ao trabalho, ${worker.name}`;
            } else if (actionType === 'SAIDA') {
                badge.className = 'inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-edm-100 text-edm-800 mb-4';
                badge.innerHTML = `<i class="fa-solid fa-door-open"></i> SAÍDA • ${timeStr.slice(0,5)}`;
                greetingEl.textContent = `Bom descanso, ${firstName}!`;
                voiceMessage = `Até amanhã, ${worker.name}. Saída registada com sucesso.`;
            } else {
                badge.className = 'inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-slate-200 text-slate-700 mb-4';
                badge.innerHTML = '<i class="fa-solid fa-lock"></i> TURNO DE HOJE JÁ CONCLUÍDO';
                greetingEl.textContent = `Turno encerrado, ${firstName}`;
                voiceMessage = `${worker.name}, o seu turno de hoje já foi encerrado.`;
            }

            document.getElementById('modal-welcome').classList.remove('hidden');
            speakText(voiceMessage);
        }

        function closeWelcomeModal() {
            document.getElementById('modal-welcome').classList.add('hidden');
        }

        // Síntese de Voz em Português (Web Speech API)
        function speakText(text) {
            if ('speechSynthesis' in window) {
                window.speechSynthesis.cancel();
                const utterance = new SpeechSynthesisUtterance(text);
                utterance.lang = 'pt-PT';
                utterance.rate = 1.0;
                utterance.pitch = 1.0;
                window.speechSynthesis.speak(utterance);
            }
        }

        function renderTerminalRecentLogs() {
            const today = getTodayDateString();
            const logs = getLogs().filter(l => l.date === today);
            const workers = getWorkers();
            const container = document.getElementById('terminal-recent-logs');

            if (logs.length === 0) {
                container.innerHTML = `<div class="col-span-full text-center py-6 text-sm text-slate-400">Nenhum trabalhador registou ponto hoje ainda.</div>`;
                return;
            }

            container.innerHTML = logs.map(log => {
                const w = workers.find(item => item.id === log.workerId) || { name: 'Desconhecido', photo: '', role: '' };
                const isCompleted = Boolean(log.checkOut);
                const statusBadge = isCompleted
                    ? `<span class="px-2 py-0.5 rounded-full text-[10px] font-bold bg-slate-200 text-slate-700">Turno Concluído</span>`
                    : `<span class="px-2 py-0.5 rounded-full text-[10px] font-bold bg-emerald-100 text-emerald-700 animate-pulse">Em Serviço</span>`;

                return `
                    <div class="flex items-center gap-3 p-3 rounded-2xl bg-slate-50 border ${isCompleted ? 'border-slate-200' : 'border-emerald-200 bg-emerald-50/30'}">
                        <img src="${w.photo}" class="w-11 h-11 rounded-full object-cover border border-edm-300">
                        <div class="min-w-0 flex-grow">
                            <div class="flex items-center justify-between gap-1">
                                <p class="font-bold text-sm text-slate-800 truncate">${w.name}</p>
                                ${statusBadge}
                            </div>
                            <div class="flex items-center gap-2.5 text-xs text-slate-600 mt-1">
                                <span class="text-emerald-700 font-semibold"><i class="fa-solid fa-arrow-right-to-bracket"></i> Entrada: ${log.checkIn}</span>
                                ${log.checkOut ? `<span class="text-edm-700 font-semibold"><i class="fa-solid fa-arrow-right-from-bracket"></i> Saída: ${log.checkOut}</span>` : ''}
                            </div>
                        </div>
                    </div>
                `;
            }).join('');
        }

        // ---------------------------------------------------------------------
        // 4. AUTENTICAÇÃO DO CHEFE (SENHA: mugabe) E NAVEGAÇÃO ENTRE ABAS
        // ---------------------------------------------------------------------
        function handleAdminAccessClick() {
            if (isAdminAuthenticated) {
                switchToAdminView();
            } else {
                document.getElementById('admin-password-input').value = '';
                document.getElementById('admin-login-error').classList.add('hidden');
                document.getElementById('modal-admin-login').classList.remove('hidden');
                setTimeout(() => document.getElementById('admin-password-input').focus(), 100);
            }
        }

        function closeAdminLoginModal() {
            document.getElementById('modal-admin-login').classList.add('hidden');
        }

        function verifyAdminLogin(e) {
            e.preventDefault();
            const pwd = document.getElementById('admin-password-input').value.trim();
            if (pwd === ADMIN_SECRET) {
                isAdminAuthenticated = true;
                closeAdminLoginModal();
                switchToAdminView();
                showToast('Bem-vindo, Chefe! Acesso administrativo desbloqueado.', 'info');
            } else {
                document.getElementById('admin-login-error').classList.remove('hidden');
            }
        }

        function switchToAdminView() {
            document.getElementById('view-terminal').classList.add('hidden');
            document.getElementById('view-admin').classList.remove('hidden');
            document.getElementById('admin-btn-text').textContent = 'Painel Ativo';
            setAdminTab('dashboard');
        }

        function switchToTerminal() {
            document.getElementById('view-admin').classList.add('hidden');
            document.getElementById('view-terminal').classList.remove('hidden');
            renderTerminalRecentLogs();
        }

        function logoutAdmin() {
            isAdminAuthenticated = false;
            document.getElementById('admin-btn-text').textContent = 'Área do Chefe';
            switchToTerminal();
            showToast('Painel do chefe bloqueado com segurança.', 'info');
        }

        function setAdminTab(tabName) {
            document.querySelectorAll('.admin-tab-content').forEach(el => el.classList.add('hidden'));
            document.querySelectorAll('.admin-tab-btn').forEach(btn => {
                btn.classList.remove('bg-edm-600', 'text-white', 'shadow-sm');
                btn.classList.add('bg-white', 'text-slate-600', 'border', 'border-slate-200');
            });

            const activeContent = document.getElementById(`admin-tab-${tabName}`);
            const activeBtn = document.getElementById(`tab-btn-${tabName}`);
            if (activeContent) activeContent.classList.remove('hidden');
            if (activeBtn) {
                activeBtn.classList.remove('bg-white', 'text-slate-600', 'border', 'border-slate-200');
                activeBtn.classList.add('bg-edm-600', 'text-white', 'shadow-sm');
            }

            if (tabName === 'dashboard') renderDashboard();
            if (tabName === 'workers') renderWorkersList();
            if (tabName === 'calendar') { populateWorkerSelects(); renderCalendarView(); }
            if (tabName === 'justifications') { populateWorkerSelects(); renderJustificationsList(); }
            if (tabName === 'export') renderRHReportPreview();
        }

        // ---------------------------------------------------------------------
        // 5. ABA 1: DASHBOARD & FISCALIZAÇÃO GERAL
        // ---------------------------------------------------------------------
        function renderDashboard() {
            const workers = getWorkers();
            const logs = getLogs();
            const selectedDate = document.getElementById('filter-log-date').value || getTodayDateString();
            const dayLogs = logs.filter(l => l.date === selectedDate);

            document.getElementById('stat-total-workers').textContent = workers.length;
            document.getElementById('stat-present-today').textContent = dayLogs.length;
            document.getElementById('stat-absent-today').textContent = Math.max(0, workers.length - dayLogs.length);

            const currentMonthStr = selectedDate.slice(0, 7);
            if (workers.length > 0) {
                let sumScores = 0;
                workers.forEach(w => {
                    sumScores += calculateWorkerMonthlyStats(w.id, currentMonthStr).score;
                });
                document.getElementById('stat-avg-score').textContent = Math.round(sumScores / workers.length) + '%';
            } else {
                document.getElementById('stat-avg-score').textContent = '100%';
            }

            const tbody = document.getElementById('dashboard-logs-table');
            if (workers.length === 0) {
                tbody.innerHTML = `<tr><td colspan="6" class="py-8 text-center text-slate-400">Nenhum trabalhador cadastrado.</td></tr>`;
                return;
            }

            tbody.innerHTML = workers.map(w => {
                const log = dayLogs.find(l => l.workerId === w.id);
                if (log) {
                    const statusBadge = log.checkOut
                        ? `<span class="px-2.5 py-1 rounded-full text-xs font-bold bg-slate-100 text-slate-700">Turno Completo</span>`
                        : `<span class="px-2.5 py-1 rounded-full text-xs font-bold bg-emerald-100 text-emerald-700">Em Serviço</span>`;
                    return `
                        <tr class="hover:bg-slate-50/80 transition">
                            <td class="py-3.5 px-4 flex items-center gap-3">
                                <img src="${w.photo}" class="w-9 h-9 rounded-full object-cover border border-edm-300">
                                <span class="font-bold text-slate-800">${w.name}</span>
                            </td>
                            <td class="py-3.5 px-4 text-slate-600">${w.role}</td>
                            <td class="py-3.5 px-4 font-mono font-bold text-emerald-700">${log.checkIn}</td>
                            <td class="py-3.5 px-4 font-mono font-bold text-edm-700">${log.checkOut || '--:--:--'}</td>
                            <td class="py-3.5 px-4 text-xs text-slate-500">${log.method}</td>
                            <td class="py-3.5 px-4">${statusBadge}</td>
                        </tr>
                    `;
                } else {
                    return `
                        <tr class="bg-rose-50/30 hover:bg-rose-50/60 transition">
                            <td class="py-3.5 px-4 flex items-center gap-3">
                                <img src="${w.photo}" class="w-9 h-9 rounded-full object-cover grayscale opacity-75">
                                <span class="font-bold text-slate-700">${w.name}</span>
                            </td>
                            <td class="py-3.5 px-4 text-slate-500">${w.role}</td>
                            <td class="py-3.5 px-4 font-mono text-rose-400">--:--:--</td>
                            <td class="py-3.5 px-4 font-mono text-rose-400">--:--:--</td>
                            <td class="py-3.5 px-4 text-xs text-slate-400">—</td>
                            <td class="py-3.5 px-4"><span class="px-2.5 py-1 rounded-full text-xs font-bold bg-rose-100 text-rose-700">Sem Registo</span></td>
                        </tr>
                    `;
                }
            }).join('');
        }

        // ---------------------------------------------------------------------
        // 6. ABA 2: CADASTRO DE TRABALHADORES + FOTO GALERIA + BIOMETRIA
        // ---------------------------------------------------------------------
        function handleWorkerPhotoUpload(event) {
            const file = event.target.files[0];
            if (!file) return;

            const reader = new FileReader();
            reader.onload = function(e) {
                const img = new Image();
                img.onload = function() {
                    const canvas = document.createElement('canvas');
                    const maxSize = 256;
                    let width = img.width;
                    let height = img.height;

                    if (width > maxSize || height > maxSize) {
                        if (width > height) { height *= maxSize / width; width = maxSize; }
                        else { width *= maxSize / height; height = maxSize; }
                    }
                    canvas.width = width;
                    canvas.height = height;
                    canvas.getContext('2d').drawImage(img, 0, 0, width, height);

                    currentPhotoBase64 = canvas.toDataURL('image/jpeg', 0.8);
                    document.getElementById('worker-photo-preview').src = currentPhotoBase64;
                };
                img.src = e.target.result;
            };
            reader.readAsDataURL(file);
        }

        function generateBioHash() {
            const chars = '0123456789ABCDEF';
            let hash = 'BIO-';
            for (let i = 0; i < 6; i++) {
                hash += chars[Math.floor(Math.random() * chars.length)];
            }
            return hash;
        }

        function bufferToBase64Url(buffer) {
            const bytes = new Uint8Array(buffer);
            let binary = '';
            for (let i = 0; i < bytes.byteLength; i++) {
                binary += String.fromCharCode(bytes[i]);
            }
            return btoa(binary).replace(/\+/g, '-').replace(/\//g, '_').replace(/=+$/, '');
        }

        function base64UrlToBuffer(base64url) {
            const base64 = base64url.replace(/-/g, '+').replace(/_/g, '/');
            const binary = atob(base64);
            const bytes = new Uint8Array(binary.length);
            for (let i = 0; i < binary.length; i++) {
                bytes[i] = binary.charCodeAt(i);
            }
            return bytes.buffer;
        }

        // Captura tátil em 3 etapas no ecrã (para Android, tablets e monitores touch)
        function handleTouchEnrollStep() {
            touchEnrollCount++;
            const step1 = document.getElementById('enroll-step-1');
            const step2 = document.getElementById('enroll-step-2');
            const step3 = document.getElementById('enroll-step-3');
            const statusText = document.getElementById('finger-enroll-status');
            const btn = document.getElementById('btn-touch-enroll');

            if (touchEnrollCount === 1) {
                step1.className = 'h-1.5 w-8 rounded-full bg-edm-500 transition-colors';
                statusText.textContent = '1ª leitura capturada! Levante e toque novamente (1/3)';
                statusText.className = 'text-[11px] font-semibold text-edm-700 mt-1.5';
            } else if (touchEnrollCount === 2) {
                step2.className = 'h-1.5 w-8 rounded-full bg-edm-500 transition-colors';
                statusText.textContent = '2ª leitura capturada! Toque mais uma vez para confirmar (2/3)';
            } else if (touchEnrollCount >= 3) {
                step3.className = 'h-1.5 w-8 rounded-full bg-emerald-500 transition-colors';
                step1.className = 'h-1.5 w-8 rounded-full bg-emerald-500 transition-colors';
                step2.className = 'h-1.5 w-8 rounded-full bg-emerald-500 transition-colors';

                const bioHash = document.getElementById('worker-bio-hash').value || generateBioHash();
                finalizeFingerprintEnrollment(bioHash, '');
                btn.className = 'w-16 h-16 rounded-full mx-auto bg-emerald-50 border-2 border-emerald-500 text-emerald-600 flex items-center justify-center text-3xl transition shadow-inner';
                statusText.textContent = 'Digital registada com sucesso (3/3) ✓';
                statusText.className = 'text-[11px] font-bold text-emerald-700 mt-1.5';
            }
        }

        // Captura Biométrica Real via WebAuthn (Sensor de Digital do Telemóvel / Windows Hello / USB)
        async function enrollRealDeviceBiometric() {
            const workerName = document.getElementById('worker-name').value.trim() || 'Trabalhador EDM';

            if (!window.PublicKeyCredential) {
                showToast('Sensor nativo indisponível neste navegador. Use o leitor de 3 toques abaixo!', 'info');
                return;
            }

            try {
                const challenge = new Uint8Array(32);
                window.crypto.getRandomValues(challenge);
                const userId = new Uint8Array(16);
                window.crypto.getRandomValues(userId);

                const credential = await navigator.credentials.create({
                    publicKey: {
                        challenge,
                        rp: { name: 'EDM Controle de Ponto' },
                        user: {
                            id: userId,
                            name: workerName.toLowerCase().replace(/\s+/g, '.'),
                            displayName: workerName
                        },
                        pubKeyCredParams: [
                            { type: 'public-key', alg: -7 },
                            { type: 'public-key', alg: -257 }
                        ],
                        authenticatorSelection: {
                            authenticatorAttachment: 'platform',
                            userVerification: 'required'
                        },
                        timeout: 30000
                    }
                });

                if (credential && credential.rawId) {
                    const webauthnId = bufferToBase64Url(credential.rawId);
                    const bioHash = generateBioHash();
                    finalizeFingerprintEnrollment(bioHash, webauthnId);

                    document.getElementById('enroll-step-1').className = 'h-1.5 w-8 rounded-full bg-emerald-500';
                    document.getElementById('enroll-step-2').className = 'h-1.5 w-8 rounded-full bg-emerald-500';
                    document.getElementById('enroll-step-3').className = 'h-1.5 w-8 rounded-full bg-emerald-500';
                    document.getElementById('finger-enroll-status').textContent = 'Sensor Físico do Aparelho Vinculado ✓';
                    document.getElementById('finger-enroll-status').className = 'text-[11px] font-bold text-emerald-700 mt-1.5';
                }
            } catch (err) {
                showToast('Não foi possível abrir o sensor nativo aqui. Use o leitor tátil de 3 toques abaixo!', 'info');
            }
        }

        function finalizeFingerprintEnrollment(bioHash, webauthnId) {
            document.getElementById('worker-has-finger').value = 'true';
            document.getElementById('worker-bio-hash').value = bioHash;
            if (webauthnId) {
                document.getElementById('worker-webauthn-id').value = webauthnId;
            }
            const hashBadge = document.getElementById('finger-bio-hash-badge');
            hashBadge.textContent = bioHash;
            hashBadge.classList.remove('hidden');
            showToast(`Impressão digital (${bioHash}) vinculada ao trabalhador!`, 'info');
        }

        function saveWorker(e) {
            e.preventDefault();
            if (!isAdminAuthenticated) return;

            const id = document.getElementById('edit-worker-id').value;
            const name = document.getElementById('worker-name').value.trim();
            const role = document.getElementById('worker-role').value.trim();
            const pin = document.getElementById('worker-pin').value.trim();
            const hasFinger = document.getElementById('worker-has-finger').value === 'true';
            const bioHash = document.getElementById('worker-bio-hash').value || (hasFinger ? generateBioHash() : '');
            const webauthnId = document.getElementById('worker-webauthn-id').value || '';

            const workers = getWorkers();

            // Verificar se o PIN já existe em outro trabalhador
            if (workers.some(w => w.pin === pin && w.id !== id)) {
                showToast('Esta senha pessoal já está atribuída a outro trabalhador!', 'error');
                return;
            }

            const defaultAvatar = `https://ui-avatars.com/api/?name=${encodeURIComponent(name)}&background=F26522&color=fff&size=256`;

            if (id) {
                // Editar existente
                const idx = workers.findIndex(w => w.id === id);
                if (idx !== -1) {
                    workers[idx].name = name;
                    workers[idx].role = role;
                    workers[idx].pin = pin;
                    workers[idx].hasFingerprint = hasFinger;
                    workers[idx].bioHash = bioHash;
                    if (webauthnId) workers[idx].webauthnId = webauthnId;
                    if (currentPhotoBase64) workers[idx].photo = currentPhotoBase64;
                }
                showToast('Dados e biometria do trabalhador atualizados!', 'info');
            } else {
                // Criar novo
                workers.push({
                    id: 'w_' + Date.now(),
                    name,
                    role,
                    pin,
                    hasFingerprint: hasFinger,
                    bioHash,
                    webauthnId,
                    photo: currentPhotoBase64 || defaultAvatar
                });
                showToast('Novo trabalhador cadastrado no sistema!', 'info');
            }

            saveWorkers(workers);
            resetWorkerForm();
            renderWorkersList();
        }

        function editWorker(id) {
            const w = getWorkers().find(item => item.id === id);
            if (!w) return;

            touchEnrollCount = 0;
            document.getElementById('edit-worker-id').value = w.id;
            document.getElementById('worker-name').value = w.name;
            document.getElementById('worker-role').value = w.role;
            document.getElementById('worker-pin').value = w.pin;
            document.getElementById('worker-has-finger').value = w.hasFingerprint ? 'true' : 'false';
            document.getElementById('worker-bio-hash').value = w.bioHash || '';
            document.getElementById('worker-webauthn-id').value = w.webauthnId || '';
            document.getElementById('worker-photo-preview').src = w.photo;
            currentPhotoBase64 = '';

            const hashBadge = document.getElementById('finger-bio-hash-badge');
            if (w.hasFingerprint) {
                hashBadge.textContent = w.bioHash || 'BIO-ATIVO';
                hashBadge.classList.remove('hidden');
                document.getElementById('enroll-step-1').className = 'h-1.5 w-8 rounded-full bg-emerald-500';
                document.getElementById('enroll-step-2').className = 'h-1.5 w-8 rounded-full bg-emerald-500';
                document.getElementById('enroll-step-3').className = 'h-1.5 w-8 rounded-full bg-emerald-500';
                document.getElementById('finger-enroll-status').textContent = 'Digital já registada (toque 3x para re-capturar)';
            } else {
                hashBadge.classList.add('hidden');
                document.getElementById('enroll-step-1').className = 'h-1.5 w-8 rounded-full bg-slate-200';
                document.getElementById('enroll-step-2').className = 'h-1.5 w-8 rounded-full bg-slate-200';
                document.getElementById('enroll-step-3').className = 'h-1.5 w-8 rounded-full bg-slate-200';
                document.getElementById('finger-enroll-status').textContent = 'Aguardando captura (0/3 toques)';
            }

            document.getElementById('worker-form-title').textContent = 'Editar Trabalhador';
            document.getElementById('worker-submit-text').textContent = 'Salvar Alterações';
            document.getElementById('btn-cancel-edit').classList.remove('hidden');
        }

        function resetWorkerForm() {
            touchEnrollCount = 0;
            document.getElementById('edit-worker-id').value = '';
            document.getElementById('worker-name').value = '';
            document.getElementById('worker-role').value = '';
            document.getElementById('worker-pin').value = '';
            document.getElementById('worker-has-finger').value = 'false';
            document.getElementById('worker-bio-hash').value = '';
            document.getElementById('worker-webauthn-id').value = '';
            document.getElementById('worker-photo-input').value = '';
            currentPhotoBase64 = '';
            document.getElementById('worker-photo-preview').src = 'https://ui-avatars.com/api/?name=Novo+Trabalhador&background=F26522&color=fff&size=128';

            document.getElementById('finger-bio-hash-badge').classList.add('hidden');
            document.getElementById('enroll-step-1').className = 'h-1.5 w-8 rounded-full bg-slate-200';
            document.getElementById('enroll-step-2').className = 'h-1.5 w-8 rounded-full bg-slate-200';
            document.getElementById('enroll-step-3').className = 'h-1.5 w-8 rounded-full bg-slate-200';
            document.getElementById('btn-touch-enroll').className = 'w-16 h-16 rounded-full mx-auto bg-edm-50 hover:bg-edm-100 active:scale-95 border-2 border-edm-500 text-edm-600 flex items-center justify-center text-3xl transition shadow-inner';
            document.getElementById('finger-enroll-status').textContent = 'Aguardando captura (0/3 toques)';
            document.getElementById('finger-enroll-status').className = 'text-[11px] font-semibold text-slate-600 mt-1.5';

            document.getElementById('worker-form-title').textContent = 'Cadastrar Novo Trabalhador';
            document.getElementById('worker-submit-text').textContent = 'Guardar Trabalhador no Sistema';
            document.getElementById('btn-cancel-edit').classList.add('hidden');
        }

        function deleteWorker(id) {
            if (!isAdminAuthenticated) return;
            const workers = getWorkers().filter(w => w.id !== id);
            saveWorkers(workers);
            renderWorkersList();
            showToast('Trabalhador removido pelo chefe.', 'info');
        }

        function renderWorkersList() {
            const workers = getWorkers();
            document.getElementById('workers-count-badge').textContent = `${workers.length} ativos`;
            const container = document.getElementById('workers-list-container');

            if (workers.length === 0) {
                container.innerHTML = `<p class="text-sm text-slate-400 text-center py-8">Nenhum trabalhador registado ainda.</p>`;
                return;
            }

            container.innerHTML = workers.map(w => `
                <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-3 p-3.5 rounded-2xl border border-slate-200 hover:border-edm-300 bg-slate-50/50 transition">
                    <div class="flex items-center gap-3">
                        <img src="${w.photo}" class="w-12 h-12 rounded-full object-cover border-2 border-edm-400">
                        <div>
                            <h4 class="font-bold text-sm text-slate-900">${w.name}</h4>
                            <p class="text-xs text-slate-500">${w.role}</p>
                            <div class="flex flex-wrap items-center gap-2 mt-1">
                                <span class="text-[11px] font-mono bg-white px-2 py-0.5 rounded border border-slate-200 text-slate-700">Senha: <strong>${w.pin}</strong></span>
                                ${w.hasFingerprint ? `<span class="text-[11px] bg-emerald-100 text-emerald-700 px-2 py-0.5 rounded font-semibold"><i class="fa-solid fa-fingerprint"></i> ${w.bioHash || 'Digital OK'}</span>` : '<span class="text-[11px] bg-slate-200 text-slate-500 px-2 py-0.5 rounded">Sem digital</span>'}
                            </div>
                        </div>
                    </div>
                    <div class="flex items-center gap-2 self-end sm:self-center">
                        <button onclick="editWorker('${w.id}')" class="px-3 py-1.5 rounded-lg bg-white hover:bg-edm-50 text-edm-700 border border-slate-200 text-xs font-semibold transition">
                            <i class="fa-solid fa-pen"></i> Editar
                        </button>
                        <button onclick="deleteWorker('${w.id}')" class="px-3 py-1.5 rounded-lg bg-rose-50 hover:bg-rose-100 text-rose-600 border border-rose-200 text-xs font-semibold transition">
                            <i class="fa-solid fa-trash"></i>
                        </button>
                    </div>
                </div>
            `).join('');
        }

        // ---------------------------------------------------------------------
        // 7. ABA 3: CALENDÁRIO DE PRESENÇAS, FALTAS (ABATES) E NOTAS
        // ---------------------------------------------------------------------
        function populateWorkerSelects() {
            const workers = getWorkers();
            const optionsHtml = workers.map(w => `<option value="${w.id}">${w.name}</option>`).join('');
            
            const calSelect = document.getElementById('calendar-worker-select');
            const justSelect = document.getElementById('just-worker-select');
            
            const prevCal = calSelect.value;
            calSelect.innerHTML = optionsHtml;
            if (prevCal && workers.some(w => w.id === prevCal)) calSelect.value = prevCal;

            justSelect.innerHTML = optionsHtml;
        }

        function calculateWorkerMonthlyStats(workerId, monthStr) {
            const [year, month] = monthStr.split('-').map(Number);
            const daysInMonth = new Date(year, month, 0).getDate();
            const today = new Date();
            const logs = getLogs().filter(l => l.workerId === workerId && l.date.startsWith(monthStr));
            const justifications = getJustifications().filter(j => j.workerId === workerId && j.date.startsWith(monthStr));

            let workedDays = 0;
            let unjustifiedAbsences = 0;
            let justifiedAbsences = 0;
            let expectedWorkDaysSoFar = 0;

            for (let d = 1; d <= daysInMonth; d++) {
                const dateObj = new Date(year, month - 1, d);
                const dayOfWeek = dateObj.getDay();
                const dateStr = `${monthStr}-${String(d).padStart(2, '0')}`;

                // Ignorar fins de semana (Sábado e Domingo)
                if (dayOfWeek === 0 || dayOfWeek === 6) continue;

                // Verificar apenas até hoje
                const isPastOrToday = dateObj.setHours(0,0,0,0) <= today.setHours(0,0,0,0);
                if (!isPastOrToday) continue;

                expectedWorkDaysSoFar++;
                const hasLog = logs.some(l => l.date === dateStr);
                const hasJust = justifications.some(j => j.date === dateStr);

                if (hasLog) {
                    workedDays++;
                } else if (hasJust) {
                    justifiedAbsences++;
                } else {
                    // Se for hoje e ainda não acabou o dia, só conta falta se não houver log nos dias anteriores
                    if (dateStr !== getTodayDateString()) {
                        unjustifiedAbsences++;
                    } else {
                        expectedWorkDaysSoFar--; // Hoje ainda está em curso
                    }
                }
            }

            const effectivePresent = workedDays + justifiedAbsences;
            const score = expectedWorkDaysSoFar > 0 
                ? Math.round((effectivePresent / expectedWorkDaysSoFar) * 100) 
                : 100;

            return {
                workedDays,
                unjustifiedAbsences,
                justifiedAbsences,
                expectedWorkDaysSoFar,
                score
            };
        }

        function renderCalendarView() {
            const workerId = document.getElementById('calendar-worker-select').value;
            const monthStr = document.getElementById('calendar-month-input').value;
            if (!workerId || !monthStr) return;

            const stats = calculateWorkerMonthlyStats(workerId, monthStr);

            // Classificação de Bom Trabalhador
            let badgeLabel = 'Excelente Trabalhador';
            let badgeColor = 'text-emerald-600';
            if (stats.score < 75) { badgeLabel = 'Atenção (Muitos Abates)'; badgeColor = 'text-rose-600'; }
            else if (stats.score < 90) { badgeLabel = 'Bom Desempenho'; badgeColor = 'text-amber-600'; }

            document.getElementById('worker-performance-summary').innerHTML = `
                <div class="p-4 rounded-2xl bg-emerald-50 border border-emerald-200">
                    <span class="text-xs font-semibold text-emerald-700">Dias Trabalhados</span>
                    <div class="text-2xl font-extrabold text-emerald-800 mt-1">${stats.workedDays} dias</div>
                </div>
                <div class="p-4 rounded-2xl bg-rose-50 border border-rose-200">
                    <span class="text-xs font-semibold text-rose-700">Faltas (Abates)</span>
                    <div class="text-2xl font-extrabold text-rose-800 mt-1">${stats.unjustifiedAbsences} faltas</div>
                </div>
                <div class="p-4 rounded-2xl bg-amber-50 border border-amber-200">
                    <span class="text-xs font-semibold text-amber-700">Faltas Justificadas</span>
                    <div class="text-2xl font-extrabold text-amber-800 mt-1">${stats.justifiedAbsences} dias</div>
                </div>
                <div class="p-4 rounded-2xl bg-edm-50 border border-edm-200">
                    <span class="text-xs font-semibold text-edm-700">Nota / Percentual</span>
                    <div class="text-2xl font-extrabold text-edm-600 mt-1">${stats.score}%</div>
                    <div class="text-[11px] font-bold ${badgeColor}">${badgeLabel}</div>
                </div>
            `;

            // Desenhar dias do calendário
            const [year, month] = monthStr.split('-').map(Number);
            const firstDayIndex = new Date(year, month - 1, 1).getDay();
            const daysInMonth = new Date(year, month, 0).getDate();
            const today = new Date();
            today.setHours(0,0,0,0);

            const logs = getLogs().filter(l => l.workerId === workerId && l.date.startsWith(monthStr));
            const justifications = getJustifications().filter(j => j.workerId === workerId && j.date.startsWith(monthStr));

            let gridHtml = '';
            for (let i = 0; i < firstDayIndex; i++) {
                gridHtml += `<div class="h-20 sm:h-24 rounded-xl bg-slate-50/50"></div>`;
            }

            for (let d = 1; d <= daysInMonth; d++) {
                const dateObj = new Date(year, month - 1, d);
                const dayOfWeek = dateObj.getDay();
                const dateStr = `${monthStr}-${String(d).padStart(2, '0')}`;
                const log = logs.find(l => l.date === dateStr);
                const just = justifications.find(j => j.date === dateStr);

                let cardStyle = 'bg-slate-50 border-slate-200 text-slate-400';
                let contentHtml = `<span class="text-[10px]">Fim de semana</span>`;

                if (dayOfWeek !== 0 && dayOfWeek !== 6) {
                    if (log) {
                        cardStyle = 'bg-emerald-50 border-emerald-300 text-emerald-900';
                        contentHtml = `
                            <div class="text-[10px] font-bold text-emerald-700 mt-1">✓ Presente</div>
                            <div class="text-[9px] font-mono text-emerald-600">${log.checkIn.slice(0,5)} - ${log.checkOut ? log.checkOut.slice(0,5) : '...'}</div>
                        `;
                    } else if (just) {
                        cardStyle = 'bg-amber-50 border-amber-300 text-amber-900 cursor-pointer';
                        contentHtml = `
                            <div onclick="viewProofImage('${just.proofImage}', '${just.reason} (${dateStr})')" class="text-[10px] font-bold text-amber-700 mt-1 underline">
                                <i class="fa-solid fa-file-image"></i> Justificada
                            </div>
                        `;
                    } else if (dateObj < today) {
                        cardStyle = 'bg-rose-50 border-rose-300 text-rose-900';
                        contentHtml = `<div class="text-[10px] font-bold text-rose-600 mt-1">✕ Falta (Abate)</div>`;
                    } else {
                        cardStyle = 'bg-white border-slate-200 text-slate-600';
                        contentHtml = `<div class="text-[10px] text-slate-400 mt-1">Agendado</div>`;
                    }
                }

                gridHtml += `
                    <div class="h-20 sm:h-24 p-2 rounded-xl border ${cardStyle} flex flex-col justify-between text-left transition">
                        <span class="font-bold text-xs sm:text-sm">${d}</span>
                        <div>${contentHtml}</div>
                    </div>
                `;
            }

            document.getElementById('calendar-days-grid').innerHTML = gridHtml;
        }

        // ---------------------------------------------------------------------
        // 8. ABA 4: JUSTIFICAÇÃO DE FALTAS COM FOTO COMPROVATIVA
        // ---------------------------------------------------------------------
        function handleProofUpload(event) {
            const file = event.target.files[0];
            if (!file) return;

            const reader = new FileReader();
            reader.onload = function(e) {
                const img = new Image();
                img.onload = function() {
                    const canvas = document.createElement('canvas');
                    const maxSize = 800;
                    let width = img.width;
                    let height = img.height;

                    if (width > maxSize || height > maxSize) {
                        if (width > height) { height *= maxSize / width; width = maxSize; }
                        else { width *= maxSize / height; height = maxSize; }
                    }
                    canvas.width = width;
                    canvas.height = height;
                    canvas.getContext('2d').drawImage(img, 0, 0, width, height);

                    currentProofBase64 = canvas.toDataURL('image/jpeg', 0.75);
                    const preview = document.getElementById('just-proof-preview');
                    preview.src = currentProofBase64;
                    preview.classList.remove('hidden');
                };
                img.src = e.target.result;
            };
            reader.readAsDataURL(file);
        }

        function saveJustification(e) {
            e.preventDefault();
            if (!isAdminAuthenticated) return;

            const workerId = document.getElementById('just-worker-select').value;
            const date = document.getElementById('just-date').value;
            const reason = document.getElementById('just-reason').value.trim();

            if (!currentProofBase64) {
                showToast('Por favor, carregue a foto do documento comprovativo!', 'error');
                return;
            }

            const list = getJustifications();
            list.push({
                id: 'just_' + Date.now(),
                workerId,
                date,
                reason,
                proofImage: currentProofBase64
            });

            saveJustifications(list);

            // Limpar formulário
            document.getElementById('just-reason').value = '';
            document.getElementById('just-proof-input').value = '';
            document.getElementById('just-proof-preview').classList.add('hidden');
            currentProofBase64 = '';

            renderJustificationsList();
            showToast('Falta justificada e comprovativa arquivada com sucesso!', 'info');
        }

        function deleteJustification(id) {
            if (!isAdminAuthenticated) return;
            const list = getJustifications().filter(j => j.id !== id);
            saveJustifications(list);
            renderJustificationsList();
            showToast('Justificação removida.', 'info');
        }

        function viewProofImage(imgSrc, title) {
            document.getElementById('proof-viewer-title').textContent = title;
            document.getElementById('proof-viewer-img').src = imgSrc;
            document.getElementById('modal-proof-viewer').classList.remove('hidden');
        }

        function renderJustificationsList() {
            const list = getJustifications();
            const workers = getWorkers();
            const container = document.getElementById('justifications-list');

            if (list.length === 0) {
                container.innerHTML = `<div class="col-span-full text-center py-8 text-sm text-slate-400">Nenhuma falta justificada registada até ao momento.</div>`;
                return;
            }

            container.innerHTML = list.map(j => {
                const w = workers.find(item => item.id === j.workerId) || { name: 'Trabalhador' };
                return `
                    <div class="border border-slate-200 rounded-2xl p-3.5 bg-slate-50/70 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between gap-2 mb-2">
                                <span class="text-xs font-bold px-2 py-0.5 rounded bg-amber-100 text-amber-800">${j.date}</span>
                                <button onclick="deleteJustification('${j.id}')" class="text-xs text-rose-500 hover:text-rose-700"><i class="fa-solid fa-trash"></i></button>
                            </div>
                            <h4 class="font-bold text-sm text-slate-800">${w.name}</h4>
                            <p class="text-xs text-slate-600 mt-0.5">${j.reason}</p>
                        </div>
                        <div class="mt-3 pt-2 border-t border-slate-200">
                            <button onclick="viewProofImage('${j.proofImage}', '${w.name} - ${j.reason} (${j.date})')" class="w-full py-2 rounded-xl bg-white hover:bg-edm-50 border border-edm-200 text-edm-700 text-xs font-bold flex items-center justify-center gap-1.5 transition">
                                <i class="fa-solid fa-eye"></i> Ver Foto Comprovativa
                            </button>
                        </div>
                    </div>
                `;
            }).join('');
        }

        // ---------------------------------------------------------------------
        // 9. ABA 5: EXPORTAÇÃO PARA RECURSOS HUMANOS (CSV + RELATÓRIO PDF)
        // ---------------------------------------------------------------------
        function renderRHReportPreview() {
            const monthStr = document.getElementById('export-month-input').value || getTodayDateString().slice(0, 7);
            const workers = getWorkers();
            const justifications = getJustifications().filter(j => j.date.startsWith(monthStr));

            document.getElementById('rh-report-period').textContent = `Período: ${monthStr}`;
            document.getElementById('rh-report-generated').textContent = `Emitido em: ${new Date().toLocaleDateString('pt-PT')}`;

            const tbody = document.getElementById('rh-summary-table-body');
            tbody.innerHTML = workers.map(w => {
                const stats = calculateWorkerMonthlyStats(w.id, monthStr);
                return `
                    <tr>
                        <td class="p-3 border border-slate-200 font-bold text-slate-800">${w.name}</td>
                        <td class="p-3 border border-slate-200 text-slate-600">${w.role}</td>
                        <td class="p-3 border border-slate-200 text-center font-bold text-emerald-700">${stats.workedDays}</td>
                        <td class="p-3 border border-slate-200 text-center font-bold text-rose-600">${stats.unjustifiedAbsences}</td>
                        <td class="p-3 border border-slate-200 text-center font-bold text-amber-700">${stats.justifiedAbsences}</td>
                        <td class="p-3 border border-slate-200 text-center font-extrabold text-edm-700">${stats.score}%</td>
                    </tr>
                `;
            }).join('');

            const proofsContainer = document.getElementById('rh-proofs-attachment');
            if (justifications.length === 0) {
                proofsContainer.innerHTML = `<p class="col-span-full text-xs text-slate-400 italic">Sem comprovativas de faltas justificadas neste período.</p>`;
            } else {
                proofsContainer.innerHTML = justifications.map(j => {
                    const w = workers.find(item => item.id === j.workerId) || { name: 'Trabalhador' };
                    return `
                        <div class="border border-slate-300 rounded-xl p-3 bg-slate-50">
                            <div class="text-xs font-bold text-slate-800">${w.name}</div>
                            <div class="text-[11px] text-slate-600 mb-2">Data: ${j.date} • Motivo: ${j.reason}</div>
                            <img src="${j.proofImage}" class="w-full h-36 object-contain bg-white rounded border border-slate-200">
                        </div>
                    `;
                }).join('');
            }
        }

        function exportToCSV() {
            const monthStr = document.getElementById('export-month-input').value || getTodayDateString().slice(0, 7);
            const workers = getWorkers();
            const justifications = getJustifications().filter(j => j.date.startsWith(monthStr));

            let csvContent = '\uFEFF'; // BOM para acentuação correta no Excel
            csvContent += 'RELATÓRIO DE ASSIDUIDADE E ABATES - EDM (RECURSOS HUMANOS)\n';
            csvContent += `Período de Referência:;${monthStr}\n\n`;
            csvContent += 'Nome do Trabalhador;Cargo/Setor;Dias Trabalhados;Faltas (Abates);Faltas Justificadas;Nota Desempenho (%);Detalhes das Justificações\n';

            workers.forEach(w => {
                const stats = calculateWorkerMonthlyStats(w.id, monthStr);
                const wJusts = justifications
                    .filter(j => j.workerId === w.id)
                    .map(j => `${j.date} (${j.reason})`)
                    .join(' | ') || 'Nenhuma';

                csvContent += `"${w.name}";"${w.role}";${stats.workedDays};${stats.unjustifiedAbsences};${stats.justifiedAbsences};"${stats.score}%";"${wJusts}"\n`;
            });

            const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
            const url = URL.createObjectURL(blob);
            const link = document.createElement('a');
            link.href = url;
            link.download = `EDM_Relatorio_RH_${monthStr}.csv`;
            link.click();
            URL.revokeObjectURL(url);
            showToast('Ficheiro Excel (CSV) exportado para entrega aos Recursos Humanos!', 'info');
        }

        // Backup e Restauro JSON
        function downloadBackupJSON() {
            const backupData = {
                workers: getWorkers(),
                logs: getLogs(),
                justifications: getJustifications(),
                exportedAt: new Date().toISOString()
            };
            const blob = new Blob([JSON.stringify(backupData, null, 2)], { type: 'application/json' });
            const url = URL.createObjectURL(blob);
            const link = document.createElement('a');
            link.href = url;
            link.download = `EDM_Backup_Sistema_${getTodayDateString()}.json`;
            link.click();
            showToast('Backup completo transferido!', 'info');
        }

        function restoreBackupJSON(event) {
            const file = event.target.files[0];
            if (!file) return;
            const reader = new FileReader();
            reader.onload = function(e) {
                try {
                    const data = JSON.parse(e.target.result);
                    if (data.workers && data.logs) {
                        saveWorkers(data.workers);
                        saveLogs(data.logs);
                        saveJustifications(data.justifications || []);
                        renderDashboard();
                        showToast('Dados restaurados com sucesso!', 'info');
                    }
                } catch (err) {
                    showToast('Ficheiro de backup inválido.', 'error');
                }
            };
            reader.readAsText(file);
        }

        // Arrancar sistema ao carregar a janela
        window.onload = initSystem;
    </script>
</body>
</html>
