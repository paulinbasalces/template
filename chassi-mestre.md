# CHASSI MESTRE - PORTAL DE CURADORIA
Este documento contém a ESTRUTURA TÉCNICA 100% COMPLETA de um portal. Use a lógica e a arquitetura, mas crie um design e um conteúdo inéditos.

## 1. index.html
```html
<!DOCTYPE html>
<html lang="pt-BR" data-theme="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nome do Portal | Tagline</title>
    <meta name="description" content="Descrição focada no problema do usuário.">
    <link rel="canonical" href="[https://dominio.com/](https://dominio.com/)">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <a class="skip-link" href="#lista-ferramentas">Pular para resultados</a>

    <header class="cabecalho-site">
        <div class="container nav-bar">
            <a class="logotipo" href="./index.html">Logotipo <span>Portal</span></a>
            <div class="controles-a11y">
                <button type="button" id="btn-fonte-menos" class="btn-a11y" aria-label="Diminuir fonte">A-</button>
                <button type="button" id="btn-fonte-mais" class="btn-a11y" aria-label="Aumentar fonte">A+</button>
                <button type="button" id="btn-tema" class="btn-a11y" aria-label="Alternar tema">🌓</button>
            </div>
        </div>
    </header>

    <main class="container" id="conteudo-principal">
        <section class="hero">
            <p class="hero-kicker">Categoria Macro</p>
            <h1 class="hero-title">Título Direcionado à Dor do Público</h1>
            <p class="hero-subtitle">Subtítulo explicativo e utilitário.</p>
            
            <div class="hero-metricas">
                <span class="metrica-card"><strong id="total-ferramentas">0</strong><small>itens listados</small></span>
                <span class="metrica-card"><strong id="total-categorias">0</strong><small>categorias</small></span>
                <span class="metrica-card"><strong>100%</strong><small>verificado</small></span>
            </div>
            
            <div class="busca-container" role="search">
                <div class="busca-form">
                    <input id="campo-busca" type="search" placeholder="Busque por..." autocomplete="off">
                    <div class="busca-acoes">
                        <button type="button" id="btn-limpar-busca" class="btn-busca secundario">Limpar</button>
                    </div>
                </div>
            </div>
            
            <nav id="bento-menu" class="bento-grid-container" aria-label="Filtros"></nav>
        </section>

        <div class="area-adsense ads-vip"><p class="ads-label">Publicidade</p></div>

        <section class="painel-curadoria">
            <div>
                <p class="section-kicker">Curadoria</p>
                <h2 id="titulo-curadoria">Critérios editoriais rigorosos</h2>
                <p>Nós analisamos sistemas para garantir que você não perca tempo.</p>
            </div>
            <ul class="criterios-lista">
                <li class="criterio-card"><strong>Critério 1</strong><span>Explicação.</span></li>
                <li class="criterio-card"><strong>Critério 2</strong><span>Explicação.</span></li>
            </ul>
        </section>

        <p id="status-resultados" class="status-resultados" aria-live="polite">Carregando...</p>
        <div id="lista-ferramentas"></div>
    </main>

    <div id="modal-overlay" class="modal-overlay hidden" aria-hidden="true">
        <div class="modal-content" role="dialog" aria-modal="true">
            <button type="button" class="btn-fechar" id="fechar-modal">✕</button>
            <div class="modal-header-compacto">
                <span id="artigo-emoji" class="emoji-medio"></span>
                <div>
                    <h2 id="artigo-titulo">Título</h2>
                    <span id="artigo-categoria" class="tag-categoria">Cat</span>
                </div>
            </div>
            <div class="dor-box">
                <strong>Análise:</strong>
                <p id="artigo-dor"></p>
            </div>
            <div class="artigo-corpo">
                <p id="artigo-descricao"></p>
                <dl class="detalhes-editoriais">
                    <div><dt>Ideal Para</dt><dd id="artigo-melhor-para"></dd></div>
                    <div><dt>Ponto de Atenção</dt><dd id="artigo-cuidado"></dd></div>
                </dl>
            </div>
            <div class="acoes-ferramenta">
                <a id="artigo-link" href="#" target="_blank" class="btn-primario">Acessar Oficial</a>
                <div class="share-buttons">
                    <p class="share-title">Compartilhar:</p>
                    <div class="share-icons" id="botoes-compartilhamento"></div>
                </div>
            </div>
        </div>
    </div>

    <footer class="rodape-site">
        <div class="container">
            <p>&copy; 2026 Portal.</p>
            <nav class="links-rodape">
                <a href="sobre.html">Sobre</a>
                <a href="privacidade.html">Privacidade</a>
            </nav>
        </div>
    </footer>
    <script src="script.js"></script>
</body>
</html>
```

## 2. style.css
```css
@import url('[https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&display=swap](https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&display=swap)');

:root {
  --bg-base: #F8FAFC;
  --card-bg: #FFFFFF;
  --text-main: #0F172A;
  --text-muted: #64748B;
  --accent-primary: #6366F1; /* Roxo Neutro no Chassi */
  --accent-secondary: #334155; 
  --accent-focus: #818CF8;
  --accent-soft: #EEF2FF;
  --border-light: #E2E8F0;
  --radius-card: 16px;
  --radius-pill: 100px;
}

[data-theme="dark"] {
  --bg-base: #0B1120;
  --card-bg: #1E293B;
  --text-main: #F8FAFC;
  --text-muted: #94A3B8;
  --border-light: #334155;
  --accent-primary: #818CF8;
  --accent-soft: #312E81;
}

* { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Plus Jakarta Sans', sans-serif; }
body { background-color: var(--bg-base); color: var(--text-main); line-height: 1.6; }
.container { max-width: 1200px; margin: 0 auto; padding: 0 24px; }
.hidden { display: none !important; }

/* Acessibilidade */
.skip-link { position: absolute; top: -100px; left: 20px; background: var(--text-main); color: var(--bg-base); padding: 12px; z-index: 2000; border-radius: 8px; }
.skip-link:focus { top: 20px; }

/* Cabeçalho */
.cabecalho-site { position: sticky; top: 16px; z-index: 100; margin: 0 24px; }
.nav-bar { background: var(--card-bg); border: 1px solid var(--border-light); border-radius: var(--radius-pill); padding: 10px 24px; display: flex; justify-content: space-between; align-items: center; }
.logotipo { font-size: 1.3rem; font-weight: 800; color: var(--accent-primary); text-decoration: none; }
.btn-a11y { background: var(--bg-base); border: 1px solid var(--border-light); color: var(--text-main); font-weight: 700; border-radius: 50%; width: 40px; height: 40px; cursor: pointer; }

/* Hero */
.hero { text-align: center; padding: 60px 0 40px; }
.hero-title { font-size: 3rem; font-weight: 800; color: var(--text-main); margin-bottom: 16px; }
.hero-metricas { display: flex; justify-content: center; gap: 16px; margin-bottom: 40px; }
.metrica-card { background: var(--card-bg); border: 1px solid var(--border-light); border-radius: 12px; padding: 20px; border-bottom: 4px solid var(--accent-primary); }

/* Busca & Filtros */
.busca-form { display: flex; max-width: 700px; margin: 0 auto; background: var(--card-bg); border: 1px solid var(--border-light); border-radius: var(--radius-pill); padding: 8px; }
.busca-form input { flex: 1; border: none; background: transparent; padding: 0 20px; font-size: 1.1rem; color: var(--text-main); outline: none;}
.btn-busca { background: var(--bg-base); border: 1px solid var(--border-light); padding: 12px 24px; border-radius: var(--radius-pill); cursor: pointer; font-weight: 700; color: var(--text-main); }
.bento-grid-container { display: flex; flex-wrap: wrap; justify-content: center; gap: 12px; margin-top: 32px; }
.bento-card { background: var(--card-bg); border: 1px solid var(--border-light); padding: 10px 16px; border-radius: 12px; cursor: pointer; display: flex; gap: 8px; align-items: center; color: var(--text-main); font-weight: 600; }
.bento-card[aria-pressed="true"] { border-color: var(--accent-primary); background: var(--accent-soft); }

/* Cards & Layout */
.area-adsense { background: var(--border-light); text-align: center; border-radius: 12px; min-height: 100px; display: flex; justify-content: center; align-items: center; margin: 40px 0; }
.painel-curadoria { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; margin-bottom: 50px; }
.status-resultados { text-align: center; font-weight: 700; color: var(--text-muted); margin-bottom: 30px; }
.sessao-categoria { margin-bottom: 60px; }
.sessao-titulo { font-size: 1.8rem; border-bottom: 2px solid var(--border-light); margin-bottom: 24px; padding-bottom: 10px; }
.grid-cards { display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 24px; }
.card { background: var(--card-bg); border: 1px solid var(--border-light); border-radius: var(--radius-card); padding: 24px; display: flex; flex-direction: column; }
.card-topo { display: flex; justify-content: space-between; margin-bottom: 16px; }
.card-tag { background: var(--accent-soft); color: var(--accent-primary); padding: 4px 8px; border-radius: 6px; font-size: 0.75rem; font-weight: 800; text-transform: uppercase;}
.card h3 { font-size: 1.3rem; margin-bottom: 8px; }
.card-desc { font-weight: 700; margin-bottom: 12px; }
.card-editorial { color: var(--text-muted); flex-grow: 1; margin-bottom: 24px; }
.card-footer { display: flex; justify-content: space-between; align-items: center; border-top: 1px solid var(--border-light); padding-top: 16px; }
.btn-card-abrir { background: var(--bg-base); border: 1px solid var(--border-light); padding: 12px 16px; border-radius: 12px; cursor: pointer; font-weight: 700; color: var(--text-main); }
.link-card-oficial { color: var(--accent-primary); font-weight: 800; text-decoration: none; }

/* Modal */
.modal-overlay { position: fixed; inset: 0; background: rgba(0,0,0,0.8); z-index: 1000; display: flex; justify-content: center; align-items: center; padding: 20px; }
.modal-content { background: var(--card-bg); width: 100%; max-width: 600px; border-radius: var(--radius-card); padding: 32px; position: relative; max-height: 90vh; overflow-y: auto; }
.btn-fechar { position: absolute; top: 16px; right: 16px; background: var(--bg-base); border: 1px solid var(--border-light); width: 40px; height: 40px; border-radius: 8px; cursor: pointer; font-weight: bold; color: var(--text-main); }
.dor-box { background: var(--accent-soft); padding: 20px; border-radius: 12px; border-left: 4px solid var(--accent-primary); margin: 24px 0; }
.dor-box strong { color: var(--accent-primary); }
.detalhes-editoriais div { background: var(--bg-base); padding: 16px; border-radius: 12px; margin-bottom: 16px; }
.btn-primario { display: block; text-align: center; background: var(--accent-primary); color: #FFF; padding: 16px; border-radius: 12px; text-decoration: none; font-weight: 800; }
.btn-share { background: var(--text-main); color: var(--bg-base); padding: 12px; border-radius: 8px; border: none; cursor: pointer; font-weight: 700; width: 100%; margin-top: 16px; }

/* Institucionais */
.rodape-site { background: var(--card-bg); padding: 40px 0; text-align: center; border-top: 1px solid var(--border-light); margin-top: 60px; }
.links-rodape { display: flex; justify-content: center; gap: 16px; margin-top: 16px; }
.links-rodape a { color: var(--accent-primary); font-weight: 700; text-decoration: none; }

@media (max-width: 768px) {
  .cabecalho-site { top: 0; margin: 0; }
  .nav-bar { border-radius: 0 0 24px 24px; flex-direction: column; gap: 16px; }
  .painel-curadoria { grid-template-columns: 1fr; }
  .busca-form { flex-direction: column; border-radius: 16px; }
}
```

## 3. script.js
```javascript
document.addEventListener('DOMContentLoaded', () => {
    let baseDeDados = [];
    let categoriaAtiva = 'Todas';
    const htmlElement = document.documentElement;

    /* Acessibilidade */
    if (localStorage.getItem('tema') === 'dark') htmlElement.setAttribute('data-theme', 'dark');
    document.getElementById('btn-tema').addEventListener('click', () => {
        const isDark = htmlElement.getAttribute('data-theme') === 'dark';
        htmlElement.toggleAttribute('data-theme', !isDark);
        localStorage.setItem('tema', isDark ? 'light' : 'dark');
    });

    let fontScale = parseInt(localStorage.getItem('fontScale'), 10) || 100;
    const atualizarFonte = () => { htmlElement.style.fontSize = fontScale + '%'; localStorage.setItem('fontScale', fontScale); };
    atualizarFonte();
    document.getElementById('btn-fonte-mais').addEventListener('click', () => { if(fontScale < 130) { fontScale += 10; atualizarFonte(); } });
    document.getElementById('btn-fonte-menos').addEventListener('click', () => { if(fontScale > 90) { fontScale -= 10; atualizarFonte(); } });

    /* Fetch e Inicialização */
    fetch('dados.json').then(res => res.json()).then(data => {
        baseDeDados = data || [];
        document.getElementById('total-ferramentas').textContent = baseDeDados.length;
        document.getElementById('total-categorias').textContent = new Set(baseDeDados.map(i => i.categoria)).size;
        renderizarFiltros();
        renderizarInterface();
        abrirModalDaUrl();
    }).catch(err => {
        document.getElementById('lista-ferramentas').innerHTML = '<p style="text-align:center;">Erro ao carregar dados.</p>';
    });

    /* Busca e Filtros */
    document.getElementById('campo-busca').addEventListener('input', () => { atualizarUrlParam('q', document.getElementById('campo-busca').value); renderizarInterface(); });
    document.getElementById('btn-limpar-busca').addEventListener('click', () => { document.getElementById('campo-busca').value = ''; categoriaAtiva = 'Todas'; atualizarUrlParam('q', null); renderizarFiltros(); renderizarInterface(); });

    function renderizarFiltros() {
        const cats = ['Todas', ...new Set(baseDeDados.map(i => i.categoria))];
        const container = document.getElementById('bento-menu');
        container.innerHTML = cats.map(cat => {
            const ativo = cat === categoriaAtiva ? 'true' : 'false';
            const total = cat === 'Todas' ? baseDeDados.length : baseDeDados.filter(i => i.categoria === cat).length;
            return `<button type="button" class="bento-card" data-cat="${cat}" aria-pressed="${ativo}"><span>${cat}</span> <strong>(${total})</strong></button>`;
        }).join('');
        container.querySelectorAll('.bento-card').forEach(btn => btn.addEventListener('click', (e) => {
            categoriaAtiva = btn.dataset.cat; renderizarFiltros(); renderizarInterface();
        }));
    }

    function renderizarInterface() {
        const termo = document.getElementById('campo-busca').value.toLowerCase().normalize("NFD").replace(/[\u0300-\u036f]/g, "");
        const filtradas = baseDeDados.filter(item => {
            const textMatch = termo === '' || (item.nome + item.dor_resolvida + item.descricao).toLowerCase().normalize("NFD").replace(/[\u0300-\u036f]/g, "").includes(termo);
            const catMatch = categoriaAtiva === 'Todas' || item.categoria === categoriaAtiva;
            return textMatch && catMatch;
        });

        document.getElementById('status-resultados').textContent = `${filtradas.length} resultados.`;
        const container = document.getElementById('lista-ferramentas');
        if (!filtradas.length) { container.innerHTML = '<p style="text-align:center;">Nenhum resultado.</p>'; return; }

        const grupos = filtradas.reduce((acc, obj) => { (acc[obj.categoria] = acc[obj.categoria] || []).push(obj); return acc; }, {});
        
        container.innerHTML = Object.keys(grupos).map((cat, idx, arr) => {
            const cards = grupos[cat].map(item => `
                <article class="card">
                    <div class="card-topo"><span class="card-emoji">${item.emoji}</span><span class="card-tag">${item.categoria}</span></div>
                    <h3>${item.nome}</h3><p class="card-desc">${item.dor_resolvida}</p><p class="card-editorial">${item.descricao}</p>
                    <div class="card-footer">
                        <button class="btn-card-abrir" onclick="abrirModal('${item.id}')">Ver Detalhes</button>
                        <a class="link-card-oficial" href="${item.url}" target="_blank">Acessar ➔</a>
                    </div>
                </article>
            `).join('');
            const ad = idx < arr.length - 1 ? `<div class="area-adsense"><p class="ads-label">Publicidade</p></div>` : '';
            return `<section class="sessao-categoria"><h2 class="sessao-titulo">${cat}</h2><div class="grid-cards">${cards}</div></section>${ad}`;
        }).join('');
    }

    /* Modais e History API */
    window.abrirModal = function(id) {
        const item = baseDeDados.find(i => String(i.id) === String(id));
        if(!item) return;
        document.getElementById('artigo-emoji').textContent = item.emoji;
        document.getElementById('artigo-titulo').textContent = item.nome;
        document.getElementById('artigo-categoria').textContent = item.categoria;
        document.getElementById('artigo-dor').textContent = item.dor_resolvida;
        document.getElementById('artigo-descricao').textContent = item.descricao;
        document.getElementById('artigo-melhor-para').textContent = 'Informação estratégica.';
        document.getElementById('artigo-cuidado').textContent = 'Consulte o site oficial.';
        document.getElementById('artigo-link').href = item.url;
        
        const btnShare = document.getElementById('botoes-compartilhamento');
        btnShare.innerHTML = `<button class="btn-share" onclick="compartilhar('${item.nome}', '${item.id}')">Copiar Link / Compartilhar</button>`;
        
        document.getElementById('modal-overlay').classList.remove('hidden');
        atualizarUrlParam('modal', item.id);
    };

    document.getElementById('fechar-modal').addEventListener('click', fecharModal);
    document.getElementById('modal-overlay').addEventListener('click', (e) => { if(e.target.id === 'modal-overlay') fecharModal(); });
    
    function fecharModal() {
        document.getElementById('modal-overlay').classList.add('hidden');
        atualizarUrlParam('modal', null);
    }

    /* Utilitários */
    function atualizarUrlParam(key, value) {
        const url = new URL(window.location.href);
        if (value) url.searchParams.set(key, value); else url.searchParams.delete(key);
        window.history.replaceState({}, '', url);
    }

    function abrirModalDaUrl() {
        const modalId = new URLSearchParams(window.location.search).get('modal');
        if (modalId) window.abrirModal(modalId);
    }

    window.compartilhar = async function(nome, id) {
        const url = `${window.location.origin}${window.location.pathname}?modal=${id}`;
        if (navigator.share) {
            try { await navigator.share({ title: nome, url: url }); } catch(err){}
        } else {
            navigator.clipboard.writeText(url).then(() => alert('Link copiado!'));
        }
    };
});
```