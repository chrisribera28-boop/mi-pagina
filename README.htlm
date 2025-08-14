<!DOCTYPE html>
<html lang="ca">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Estratègia Interactiva Powertrack</title>
    
    <!-- Chosen Palette: Calm Harmony (Neutral grays with a strong blue accent) -->
    <!-- Application Structure Plan: The SPA is structured as a "strategic fly-through" rather than a linear document. It begins with the core brand message, then moves to an interactive customer acquisition funnel where users can click each stage (Awareness, Consideration, Decision) to reveal detailed strategies. It concludes with a dashboard for budget and KPIs. This structure was chosen to transform the static report into a dynamic story, helping users understand the flow and interconnection of strategic actions, from initial contact to final measurement. -->
    <!-- Visualization & Content Choices: 
        - Core Message: Presented as a high-impact heading (HTML/CSS) to establish the key takeaway immediately.
        - Acquisition Funnel: Built as a clickable diagram (HTML/Tailwind Flexbox) to visually represent the customer journey. Interaction (Vanilla JS) dynamically updates a content panel, revealing text from the report on demand. This prevents information overload.
        - Budget Allocation: Visualized with a Donut chart (Chart.js on Canvas) to clearly show the parts of the whole budget. It's interactive on hover.
        - KPIs: Displayed as a clean, icon-based list (HTML/CSS) for quick reference.
        - Justification: This interactive, non-linear approach is more engaging and aids in better retention of the strategic plan compared to a static text document.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->

    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc; /* slate-50 */
            color: #334155; /* slate-700 */
        }
        .card {
            background-color: white;
            border-radius: 0.75rem;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.07), 0 2px 4px -2px rgb(0 0 0 / 0.07);
            transition: all 0.3s ease-in-out;
        }
        .funnel-stage {
            cursor: pointer;
            border: 2px solid transparent;
            transition: all 0.3s ease-in-out;
        }
        .funnel-stage:hover {
            transform: translateY(-4px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
        }
        .funnel-stage.active {
            border-color: #3b82f6; /* blue-500 */
            background-color: #eff6ff; /* blue-50 */
        }
        .content-pane {
            min-height: 300px;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 320px;
            margin-left: auto;
            margin-right: auto;
            height: 320px;
        }
    </style>
</head>
<body class="antialiased">

    <div class="container mx-auto p-4 sm:p-6 lg:p-8 max-w-6xl">

        <!-- Header -->
        <header class="text-center mb-12">
            <h1 class="text-3xl md:text-4xl font-bold text-slate-800 tracking-tight">La Nostra Estratègia: Atac Quirúrgic i Credibilitat</h1>
            <p class="mt-3 text-lg text-slate-600 max-w-3xl mx-auto">Aquesta no és una simple campanya. És un pla calculat per conquerir el mercat, combinant resultats immediats amb la construcció d'una marca indestructible.</p>
        </header>

        <!-- Section 1: Core Pillar -->
        <section id="pilar" class="mb-16">
            <div class="card p-8 text-center bg-slate-800 text-white">
                <h2 class="text-2xl md:text-3xl font-bold mb-2">El Pilar Fonamental: L'Aval de Metso</h2>
                <p class="md:text-xl">La nostra arma més poderosa no és el preu, és la confiança. Ens posicionem com l'extensió intel·ligent i assequible de Metso, eliminant el principal obstacle de venda: la por al desconegut.</p>
                <p class="mt-4 text-lg font-semibold bg-slate-700 p-3 rounded-lg inline-block">"La fiabilitat i tecnologia de Metso, ara a un preu que et pots permetre."</p>
            </div>
        </section>

        <!-- Section 2: The Funnel -->
        <section id="embut" class="mb-16">
            <div class="text-center mb-8">
                <h2 class="text-3xl font-bold text-slate-800">L'Embut de Captació Interactiu</h2>
                <p class="mt-2 text-lg text-slate-600">Cada etapa del viatge del client està dissenyada amb precisió. Fes clic a cada fase per descobrir la tàctica i el raonament que hi ha al darrere.</p>
            </div>
            <div class="flex flex-col lg:flex-row gap-8">
                <!-- Funnel Stages -->
                <div class="w-full lg:w-1/3 space-y-4">
                    <div id="stage-3" class="card p-6 funnel-stage">
                        <h3 class="font-bold text-xl text-slate-800">Prioritat 3: Sembrar per al Futur</h3>
                        <p class="text-slate-600">Construcció de relacions a llarg termini.</p>
                    </div>
                    <div id="stage-2" class="card p-6 funnel-stage">
                        <h3 class="font-bold text-xl text-slate-800">Prioritat 2: Construir el Fort Digital</h3>
                        <p class="text-slate-600">El nostre comercial 24/7 per convèncer.</p>
                    </div>
                    <div id="stage-1" class="card p-6 funnel-stage active">
                        <h3 class="font-bold text-xl text-slate-800">Prioritat 1: Atacar la Demanda Activa</h3>
                        <p class="text-slate-600">Resultats ràpids i directes.</p>
                    </div>
                </div>
                <!-- Content Pane -->
                <div class="w-full lg:w-2/3">
                    <div id="content-pane" class="card p-8 content-pane">
                        <!-- Content will be injected here by JS -->
                    </div>
                </div>
            </div>
        </section>

        <!-- Section 3: Budget & KPIs -->
        <section id="mesura">
            <div class="text-center mb-8">
                <h2 class="text-3xl font-bold text-slate-800">El Motor: Pressupost i Mesura</h2>
                <p class="mt-2 text-lg text-slate-600">La nostra estratègia es basa en dades. Aquí veuràs com invertim cada euro i com mesurem l'èxit.</p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
                <!-- Budget Chart -->
                <div class="card p-6">
                    <h3 class="text-xl font-bold text-center mb-4 text-slate-800">Distribució del Pressupost Inicial (2.000€)</h3>
                    <div class="chart-container">
                        <canvas id="budgetChart"></canvas>
                    </div>
                </div>
                <!-- KPIs -->
                <div class="card p-6">
                    <h3 class="text-xl font-bold mb-4 text-slate-800">Indicadors Clau d'Èxit (KPIs)</h3>
                    <ul class="space-y-4">
                        <li class="flex items-start">
                            <span class="text-blue-500 mr-3 mt-1">●</span>
                            <div>
                                <h4 class="font-semibold">Vendes i Leads</h4>
                                <p class="text-slate-600">El nostre objectiu final. Mesurarem el nombre de màquines venudes i formularis de pressupost rebuts.</p>
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="text-blue-500 mr-3 mt-1">●</span>
                            <div>
                                <h4 class="font-semibold">Tràfic i Conversions Web</h4>
                                <p class="text-slate-600">Amb Google Analytics 4, sabrem no només qui ens visita, sinó quines accions realitzen i quins canals són més efectius.</p>
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="text-blue-500 mr-3 mt-1">●</span>
                            <div>
                                <h4 class="font-semibold">Optimització Contínua</h4>
                                <p class="text-slate-600">Analitzarem quins anuncis i paraules clau generen més resultats per reinvertir el pressupost de manera intel·ligent.</p>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </section>

    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const strategyContent = {
                'stage-1': {
                    title: 'Prioritat 1: Atacar la Demanda Activa (Google Ads)',
                    content: `
                        <p class="mb-4">No podem esperar que els clients ens trobin. Hem d'anar on ja estan buscant activament una solució. Aquesta és la inversió amb el retorn més ràpid i directe.</p>
                        <h4 class="font-semibold mb-2">Per què Google Ads?</h4>
                        <p>Perquè ens permet interceptar clients en el moment exacte de màxima intenció de compra (quan busquen "comprar trituradora" o "preu machacadora"). És on es troben els clients més qualificats, aquells que tenen un problema i necessiten una solució ara.</p>
                        <div class="mt-4 p-4 bg-slate-100 rounded-lg">
                            <p class="font-bold">Acció Clau: Destinar la major part del pressupost inicial (1.500€) a aquesta plataforma per generar els primers leads de qualitat.</p>
                        </div>
                    `
                },
                'stage-2': {
                    title: 'Prioritat 2: Construir el Nostre Fort Digital (Web i Contingut)',
                    content: `
                        <p class="mb-4">Un cop captem l'atenció d'un client potencial, la nostra web ha de fer la feina de convèncer. És el nostre comercial 24/7 i ha de ser impecable.</p>
                        <h4 class="font-semibold mb-2">Per què una web optimitzada i un vídeo?</h4>
                        <ul class="list-disc list-inside space-y-2">
                            <li><strong>Web Ràpida i Clara:</strong> Ha de transmetre la nostra proposta de valor (garantia, servei, logística) en menys de 10 segons.</li>
                            <li><strong>El Vídeo:</strong> És l'eina de credibilitat definitiva. Mostra la màquina funcionant, demostrant que som una empresa real, transparent i professional.</li>
                        </ul>
                        <div class="mt-4 p-4 bg-slate-100 rounded-lg">
                            <p class="font-bold">Acció Clau: Assegurar que la web té un formulari de contacte visible a totes les pàgines i el vídeo en un lloc destacat.</p>
                        </div>
                    `
                },
                'stage-3': {
                    title: 'Prioritat 3: Sembrar per al Futur (LinkedIn i Email)',
                    content: `
                        <p class="mb-4">La venda B2B és una marató, no un esprint. La confiança es construeix amb el temps i les relacions són fonamentals.</p>
                        <h4 class="font-semibold mb-2">Per què LinkedIn i no altres xarxes?</h4>
                        <p>Perquè és on hi ha els decisors: caps de compra, gerents de planta i propietaris. Encara que no comprin directament des de LinkedIn, l'utilitzen per investigar proveïdors. La nostra presència allà ens posiciona com a experts i genera una familiaritat que serà clau en futures decisions de compra. L'emailing ens permetrà mantenir viva la relació amb els leads que encara no estan a punt per comprar.</p>
                        <div class="mt-4 p-4 bg-slate-100 rounded-lg">
                           <p class="font-bold">Acció Clau: Connectar amb directius del sector, compartir contingut de valor (articles, vídeos) i construir una base de dades per a un butlletí mensual.</p>
                        </div>
                    `
                }
            };

            const contentPane = document.getElementById('content-pane');
            const funnelStages = document.querySelectorAll('.funnel-stage');

            function updateContent(stageId) {
                const data = strategyContent[stageId];
                contentPane.innerHTML = `
                    <h3 class="text-2xl font-bold text-slate-800 mb-4">${data.title}</h3>
                    ${data.content}
                `;

                funnelStages.forEach(stage => {
                    stage.classList.remove('active');
                });
                document.getElementById(stageId).classList.add('active');
            }

            funnelStages.forEach(stage => {
                stage.addEventListener('click', () => {
                    updateContent(stage.id);
                });
            });

            // Initial content
            updateContent('stage-1');

            // Budget Chart
            const ctx = document.getElementById('budgetChart').getContext('2d');
            new Chart(ctx, {
                type: 'doughnut',
                data: {
                    labels: ['Google Ads', 'Creació de Contingut'],
                    datasets: [{
                        label: 'Pressupost',
                        data: [1500, 500],
                        backgroundColor: [
                            '#3b82f6', // blue-500
                            '#93c5fd', // blue-300
                        ],
                        borderColor: '#ffffff',
                        borderWidth: 4
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    cutout: '70%',
                    plugins: {
                        legend: {
                            position: 'bottom',
                            labels: {
                                padding: 20,
                                font: {
                                    size: 14,
                                }
                            }
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    let label = context.label || '';
                                    if (label) {
                                        label += ': ';
                                    }
                                    if (context.parsed !== null) {
                                        label += new Intl.NumberFormat('ca-ES', { style: 'currency', currency: 'EUR' }).format(context.parsed);
                                    }
                                    return label;
                                }
                            }
                        }
                    }
                }
            });
        });
    </script>

</body>
</html>
