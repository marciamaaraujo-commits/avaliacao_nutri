# avaliacao_nutri
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guia Mestre de Estudos em Nutrição</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap');
        @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@700;800&display=swap');
        
        body { font-family: 'Roboto', sans-serif; background-color: #f3f4f6; color: #334155; }
        
        /* Layout */
        .main-container { display: flex; min-height: 100vh; }
        
        /* Sidebar (Menu) */
        .sidebar {
            width: 280px;
            background-color: #1e293b;
            color: white;
            position: fixed;
            height: 100vh;
            overflow-y: auto;
            padding: 20px;
            box-shadow: 4px 0 10px rgba(0,0,0,0.1);
        }
        
        .sidebar h1 {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.5rem;
            margin-bottom: 30px;
            color: #38bdf8;
            text-transform: uppercase;
            border-bottom: 2px solid #334155;
            padding-bottom: 10px;
        }

        .menu-item {
            display: block;
            padding: 12px 15px;
            color: #cbd5e1;
            text-decoration: none;
            border-radius: 8px;
            margin-bottom: 5px;
            transition: all 0.3s;
            font-weight: 500;
        }
        
        .menu-item:hover, .menu-item.active {
            background-color: #334155;
            color: #38bdf8;
            padding-left: 20px;
        }
        
        .menu-item i { margin-right: 10px; width: 20px; text-align: center; }

        /* Content Area */
        .content {
            flex: 1;
            margin-left: 280px;
            padding: 40px;
            max-width: 1200px;
        }

        /* Sections */
        .section {
            background: white;
            border-radius: 12px;
            padding: 40px;
            margin-bottom: 40px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            scroll-margin-top: 20px;
        }

        .section-header {
            font-family: 'Montserrat', sans-serif;
            font-size: 2rem;
            color: #0f172a;
            margin-bottom: 20px;
            border-bottom: 4px solid #e2e8f0;
            padding-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        /* Tabelas Unificadas */
        table { width: 100%; border-collapse: collapse; margin: 20px 0; font-size: 0.95rem; }
        th { background-color: #334155; color: white; padding: 12px; text-align: left; }
        td { padding: 10px; border-bottom: 1px solid #e2e8f0; vertical-align: top; }
        tr:nth-child(even) { background-color: #f8fafc; }

        /* Tags e Destaques */
        .tag { display: inline-block; padding: 2px 8px; border-radius: 4px; font-size: 0.75rem; font-weight: bold; text-transform: uppercase; margin-right: 5px; }
        .tag-red { background: #fee2e2; color: #991b1b; }
        .tag-green { background: #dcfce7; color: #166534; }
        .tag-blue { background: #dbeafe; color: #1e40af; }
        .tag-orange { background: #ffedd5; color: #9a3412; }

        .note-box {
            background-color: #fffbeb;
            border-left: 5px solid #fbbf24;
            padding: 15px;
            margin-top: 20px;
            color: #92400e;
        }

        /* Botão de Impressão */
        .print-btn {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background-color: #0ea5e9;
            color: white;
            padding: 15px 25px;
            border-radius: 50px;
            font-weight: bold;
            box-shadow: 0 4px 15px rgba(14, 165, 233, 0.4);
            cursor: pointer;
            transition: transform 0.2s;
            z-index: 100;
            border: none;
        }
        .print-btn:hover { transform: scale(1.05); background-color: #0284c7; }

        /* Estilo de Impressão */
        @media print {
            .sidebar, .print-btn { display: none; }
            .content { margin: 0; padding: 0; max-width: 100%; }
            .section { box-shadow: none; border: 1px solid #ddd; break-inside: avoid; }
            body { background: white; color: black; }
            a { text-decoration: none; color: black; }
        }
    </style>
</head>
<body>

    <button class="print-btn" onclick="window.print()">
        <i class="fas fa-print"></i> Imprimir Guia Completo
    </button>

    <div class="main-container">
        
        <!-- MENU LATERAL -->
        <nav class="sidebar">
            <h1><i class="fas fa-book-reader"></i> Guia Nutri</h1>
            <a href="#intro" class="menu-item active"><i class="fas fa-home"></i> Introdução</a>
            <a href="#clinica" class="menu-item"><i class="fas fa-heartbeat"></i> Nutrição Clínica</a>
            <a href="#renal" class="menu-item"><i class="fas fa-kidneys"></i> Doença Renal</a>
            <a href="#exames" class="menu-item"><i class="fas fa-vial"></i> Exames Bioquímicos</a>
            <a href="#farmaco" class="menu-item"><i class="fas fa-pills"></i> Interações Farmaco</a>
            <a href="#micronutrientes" class="menu-item"><i class="fas fa-apple-alt"></i> Vitaminas & Minerais</a>
            <a href="#uan" class="menu-item"><i class="fas fa-utensils"></i> UAN & Temperaturas</a>
            <a href="#pratica" class="menu-item"><i class="fas fa-clipboard-check"></i> Roteiro de Estágio</a>
            <a href="#dmri" class="menu-item"><i class="fas fa-eye"></i> Tópico Especial: DMRI</a>
        </nav>

        <!-- CONTEÚDO -->
        <div class="content">

            <!-- CAPA -->
            <div id="intro" class="section text-center">
                <h2 class="text-4xl font-extrabold text-slate-800 mb-4">Guia Mestre de Estudos em Nutrição</h2>
                <p class="text-xl text-slate-500">Compilação completa para Provas Finais, Concursos e Prática Clínica.</p>
                <div class="mt-8 grid grid-cols-3 gap-4 text-left">
                    <div class="p-4 bg-blue-50 rounded border border-blue-100">
                        <h3 class="font-bold text-blue-800">Clínica & Patologia</h3>
                        <p class="text-sm">Diabetes, Cardio, TGI, Renal, Oncologia.</p>
                    </div>
                    <div class="p-4 bg-green-50 rounded border border-green-100">
                        <h3 class="font-bold text-green-800">Ciência dos Alimentos</h3>
                        <p class="text-sm">UAN, Temperaturas, Higiene.</p>
                    </div>
                    <div class="p-4 bg-purple-50 rounded border border-purple-100">
                        <h3 class="font-bold text-purple-800">Bioquímica</h3>
                        <p class="text-sm">Exames, Vitaminas, Interações.</p>
                    </div>
                </div>
            </div>

            <!-- 1. NUTRIÇÃO CLÍNICA -->
            <div id="clinica" class="section">
                <div class="section-header text-blue-600"><i class="fas fa-stethoscope"></i> Nutrição Clínica Geral</div>
                
                <h3><i class="fas fa-fire text-amber-500"></i> Metabolismo & Endócrino</h3>
                <table>
                    <tr>
                        <th width="20%">Doença</th>
                        <th width="40%">Estratégia Nutricional</th>
                        <th width="40%">Deficiências / Riscos</th>
                    </tr>
                    <tr>
                        <td><strong>Obesidade</strong></td>
                        <td>Deficit calórico moderado, ↑ Fibras, ↓ Ultraprocessados. Foco comportamental.</td>
                        <td>Vit D (sequestro no tecido adiposo), Ferro (inflamação).</td>
                    </tr>
                    <tr>
                        <td><strong>Diabetes (1 e 2)</strong></td>
                        <td>Contagem de CHO, Baixo Índice Glicêmico, Fracionamento.</td>
                        <td>Magnésio (perda urinária), B12 (uso prolongado de Metformina).</td>
                    </tr>
                    <tr>
                        <td><strong>Dislipidemias</strong></td>
                        <td>↓ Gordura Saturada/Trans, ↑ Fitoesteróis, ↑ Ômega-3. ↓ Açúcar (p/ Triglicérides).</td>
                        <td>Coenzima Q10 (uso de estatinas).</td>
                    </tr>
                </table>

                <h3><i class="fas fa-heart text-red-500"></i> Cardiovascular</h3>
                <table>
                    <tr>
                        <th width="20%">Doença</th>
                        <th width="40%">Estratégia Nutricional</th>
                        <th width="40%">Deficiências / Riscos</th>
                    </tr>
                    <tr>
                        <td><strong>Hipertensão (HAS)</strong></td>
                        <td>Dieta DASH, < 2g Sódio/dia, Rica em K, Mg e Ca.</td>
                        <td>Potássio, Magnésio (especialmente se usar diuréticos).</td>
                    </tr>
                    <tr>
                        <td><strong>Insuf. Cardíaca</strong></td>
                        <td>Restrição de Sódio e Líquidos (se edema), Textura leve (evitar fadiga).</td>
                        <td>Tiamina (B1 - depleta com diuréticos de alça).</td>
                    </tr>
                </table>

                <h3><i class="fas fa-utensils text-emerald-500"></i> Trato Gastrointestinal (TGI)</h3>
                <table>
                    <tr>
                        <td><strong>DRGE (Refluxo)</strong></td>
                        <td>↓ Volume, ↓ Gorduras, ↓ Cafeína/Menta. Não deitar pós-refeição.</td>
                    </tr>
                    <tr>
                        <td><strong>Doença Celíaca</strong></td>
                        <td>Isenção TOTAL de Glúten. Cuidado com contaminação cruzada.</td>
                    </tr>
                    <tr>
                        <td><strong>DII (Crohn/RCU)</strong></td>
                        <td><strong>Crise:</strong> Pobre em resíduos. <strong>Remissão:</strong> Saudável. Repor Ferro/B12.</td>
                    </tr>
                    <tr>
                        <td><strong>Esteatose Hepática</strong></td>
                        <td>Perda de peso (7-10%), ↓ Frutose, ↓ Gordura saturada.</td>
                    </tr>
                </table>
            </div>

            <!-- 2. DOENÇA RENAL -->
            <div id="renal" class="section">
                <div class="section-header text-sky-600"><i class="fas fa-kidneys"></i> Nutrição Renal (A Inversão)</div>
                <div class="note-box">
                    <strong>Regra de Ouro:</strong> O tratamento muda radicalmente quando o paciente entra em diálise.
                </div>
                <br>
                <table>
                    <thead>
                        <tr>
                            <th>Fase</th>
                            <th>Proteína (g/kg)</th>
                            <th>Minerais (Na, K, P)</th>
                            <th>Objetivo</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr class="bg-blue-50">
                            <td><strong>Conservador (Pré-Diálise)</strong></td>
                            <td class="text-blue-800 font-bold">0,6 (Hipoproteica)</td>
                            <td>Restrição rigorosa se exames alterados.</td>
                            <td>Poupar o rim, adiar diálise.</td>
                        </tr>
                        <tr class="bg-red-50">
                            <td><strong>Hemodiálise (HD)</strong></td>
                            <td class="text-red-800 font-bold">1,2 (Hiperproteica)</td>
                            <td>Restrição severa de Líquidos, K e P.</td>
                            <td>Repor perdas da máquina.</td>
                        </tr>
                        <tr class="bg-yellow-50">
                            <td><strong>Litíase (Pedra)</strong></td>
                            <td>0,8 - 1,0 (Normal)</td>
                            <td><strong>NUNCA restringir Cálcio</strong>. ↑ Água (>2,5L).</td>
                            <td>Diluir urina, evitar oxalato.</td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <!-- 3. EXAMES LABORATORIAIS -->
            <div id="exames" class="section">
                <div class="section-header text-purple-600"><i class="fas fa-vial"></i> Interpretação de Exames</div>
                
                <div class="grid grid-cols-2 gap-6">
                    <div>
                        <h4 class="font-bold text-slate-700 border-b mb-2">Hemograma & Anemia</h4>
                        <ul class="list-disc list-inside text-sm space-y-2">
                            <li><strong>Hb/Ht Baixos:</strong> Anemia.</li>
                            <li><strong>VCM Baixo (<80):</strong> Falta de Ferro (Microcítica).</li>
                            <li><strong>VCM Alto (>100):</strong> Falta de B12/Folato (Macrocítica).</li>
                            <li><strong>Ferritina:</strong> Estoque de ferro (Sobe na inflamação!).</li>
                        </ul>
                    </div>
                    <div>
                        <h4 class="font-bold text-slate-700 border-b mb-2">Inflamação & Estado Nutricional</h4>
                        <ul class="list-disc list-inside text-sm space-y-2">
                            <li><strong>PCR:</strong> Marcador de inflamação aguda.</li>
                            <li><strong>Albumina:</strong> Sobe na desidratação, cai na inflamação. <span class="text-red-600 font-bold">Não</span> diagnostica desnutrição se PCR estiver alta.</li>
                        </ul>
                    </div>
                    <div>
                        <h4 class="font-bold text-slate-700 border-b mb-2">Rim & Fígado</h4>
                        <ul class="list-disc list-inside text-sm space-y-2">
                            <li><strong>Creatinina:</strong> Sobe quando rim falha.</li>
                            <li><strong>Ureia:</strong> Sobe na desidratação ou dieta hiperproteica.</li>
                            <li><strong>TGP (ALT):</strong> Lesão específica do fígado.</li>
                            <li><strong>Gama-GT:</strong> Marcador de álcool ou obstrução biliar.</li>
                        </ul>
                    </div>
                    <div>
                        <h4 class="font-bold text-slate-700 border-b mb-2">Metabolismo</h4>
                        <ul class="list-disc list-inside text-sm space-y-2">
                            <li><strong>HbA1c:</strong> Diabetes (Normal < 5,7% | DM > 6,5%).</li>
                            <li><strong>Triglicérides:</strong> Sobe com açúcar/álcool.</li>
                            <li><strong>LDL:</strong> Risco cardiovascular.</li>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- 4. INTERAÇÕES FARMACOLÓGICAS -->
            <div id="farmaco" class="section">
                <div class="section-header text-red-600"><i class="fas fa-pills"></i> Interações Droga-Nutriente</div>
                <table>
                    <tr>
                        <th>Medicamento</th>
                        <th>Interação Chave (Nutrição)</th>
                    </tr>
                    <tr>
                        <td><strong>Varfarina</strong></td>
                        <td><span class="tag tag-red">Vit K</span> Folhas verdes alteram coagulação. Manter ingestão constante.</td>
                    </tr>
                    <tr>
                        <td><strong>Levotiroxina</strong></td>
                        <td><span class="tag tag-red">Jejum</span> Cálcio, Ferro, Soja e Fibras bloqueiam absorção. Jejum de 1h.</td>
                    </tr>
                    <tr>
                        <td><strong>Metformina</strong></td>
                        <td><span class="tag tag-blue">B12</span> Uso crônico reduz absorção de Vitamina B12.</td>
                    </tr>
                    <tr>
                        <td><strong>Furosemida</strong></td>
                        <td><span class="tag tag-blue">Minerais</span> Perda urinária de Potássio, Magnésio e Tiamina.</td>
                    </tr>
                    <tr>
                        <td><strong>Tetraciclina</strong></td>
                        <td><span class="tag tag-red">Cálcio</span> Leite/Queijo anulam o antibiótico. Tomar com água.</td>
                    </tr>
                    <tr>
                        <td><strong>Levodopa</strong></td>
                        <td><span class="tag tag-red">Proteína</span> Compete na absorção. Concentrar proteína no jantar.</td>
                    </tr>
                </table>
            </div>

            <!-- 5. VITAMINAS E MINERAIS -->
            <div id="micronutrientes" class="section">
                <div class="section-header text-orange-600"><i class="fas fa-carrot"></i> Vitaminas & Minerais</div>
                <p class="mb-4">Resumo das deficiências clássicas para provas.</p>
                <table>
                    <tr>
                        <td><strong>Vit A</strong></td>
                        <td>Cegueira Noturna, Xeroftalmia.</td>
                    </tr>
                    <tr>
                        <td><strong>Vit D</strong></td>
                        <td>Raquitismo, Osteomalácia. Fonte principal: Sol.</td>
                    </tr>
                    <tr>
                        <td><strong>Vit C</strong></td>
                        <td>Escorbuto (sangramento gengival). Melhora absorção de Ferro.</td>
                    </tr>
                    <tr>
                        <td><strong>B1 (Tiamina)</strong></td>
                        <td>Beribéri, Encefalopatia de Wernicke (alcoólatras).</td>
                    </tr>
                    <tr>
                        <td><strong>B3 (Niacina)</strong></td>
                        <td>Pelagra (3Ds: Dermatite, Diarreia, Demência).</td>
                    </tr>
                    <tr>
                        <td><strong>B12</strong></td>
                        <td>Anemia Perniciosa, danos neurológicos. Exclusiva animal.</td>
                    </tr>
                    <tr>
                        <td><strong>Ferro</strong></td>
                        <td>Anemia Ferropriva (Microcítica).</td>
                    </tr>
                    <tr>
                        <td><strong>Zinco</strong></td>
                        <td>Baixa imunidade, perda de paladar, cicatrização lenta.</td>
                    </tr>
                </table>
            </div>

            <!-- 6. UAN -->
            <div id="uan" class="section">
                <div class="section-header text-amber-600"><i class="fas fa-temperature-high"></i> UAN & Segurança Alimentar</div>
                
                <div class="grid grid-cols-2 gap-8">
                    <div>
                        <h4 class="font-bold text-red-600">Temperaturas Críticas</h4>
                        <ul class="list-none space-y-2 mt-2">
                            <li>🔥 <strong>Cocção:</strong> > 70°C no centro.</li>
                            <li>♨️ <strong>Reaquecimento:</strong> > 74°C.</li>
                            <li>🍲 <strong>Distribuição Quente:</strong> > 60°C (máx 6h).</li>
                            <li>🥗 <strong>Distribuição Fria:</strong> < 10°C (máx 4h).</li>
                            <li>❄️ <strong>Congelado:</strong> -18°C.</li>
                        </ul>
                    </div>
                    <div>
                        <h4 class="font-bold text-blue-600">Conceitos Chave</h4>
                        <ul class="list-none space-y-2 mt-2">
                            <li><strong>Zona de Perigo:</strong> Entre 10°C e 60°C (bactérias multiplicam).</li>
                            <li><strong>FC (Correção):</strong> Limpeza (Sempre > 1).</li>
                            <li><strong>IC (Cocção):</strong> Cozimento (Pode ser < 1 ou > 1).</li>
                            <li><strong>Binômio:</strong> Tempo x Temperatura.</li>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- 7. ROTEIRO PRÁTICO -->
            <div id="pratica" class="section">
                <div class="section-header text-green-600"><i class="fas fa-clipboard-check"></i> Roteiro de Prova Prática</div>
                
                <h4 class="font-bold mt-4">1. Antropometria</h4>
                <p>Saiba medir dobras (não soltar a pinça ao ler) e altura de joelho (Chumlea). IMC = P/A².</p>

                <h4 class="font-bold mt-4">2. Anamnese</h4>
                <p>Não induza respostas. Pergunte sobre alergias, funcionamento intestinal e mastigação.</p>

                <h4 class="font-bold mt-4">3. Hospitalar</h4>
                <p>Segurança em primeiro lugar. Risco de disfagia? Suspenda oral e peça fono. Cálculo de enteral (kcal/kg).</p>

                <h4 class="font-bold mt-4">4. Saúde Pública</h4>
                <p>Curvas da OMS (Z-Score). EAN com linguagem simples (comida, não nutriente).</p>
            </div>

            <!-- 8. TÓPICO ESPECIAL: DMRI -->
            <div id="dmri" class="section">
                <div class="section-header text-indigo-600"><i class="fas fa-eye"></i> Tópico Especial: DMRI</div>
                <p class="text-sm text-gray-500 mb-4">Baseado no TCC: "Conhecimento sobre Alimentação e DMRI"</p>
                
                <div class="bg-indigo-50 p-6 rounded-lg border border-indigo-200">
                    <h3 class="font-bold text-indigo-800">Degeneração Macular Relacionada à Idade</h3>
                    <p class="mt-2"><strong>O que é?</strong> Principal causa de cegueira em idosos. Afeta a mácula (visão central).</p>
                    <p class="mt-2"><strong>Nutrição Protetora (Estudo AREDS):</strong></p>
                    <ul class="list-disc list-inside mt-1 text-indigo-900">
                        <li><strong>Luteína e Zeaxantina:</strong> Carotenoides amarelos (filtram luz azul). Fontes: Couve, espinafre, milho, gema.</li>
                        <li><strong>Zinco:</strong> Mineral essencial para a retina.</li>
                        <li><strong>Ômega-3:</strong> Anti-inflamatório.</li>
                        <li><strong>Antioxidantes:</strong> Vitaminas C e E.</li>
                    </ul>
                    <p class="mt-4 font-bold text-red-600">Alerta:</p>
                    <p>Muitos profissionais de saúde desconhecem essa relação, perdendo a chance de prevenção. O TCC identificou essa lacuna na formação.</p>
                </div>
            </div>

        </div>
    </div>

</body>
</html>
