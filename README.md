# 🏷️ WellShop — Catálogo de Produtos Afiliados

Site de catálogo moderno para divulgar e gerenciar produtos afiliados da **Shopee**, **Amazon** e **Mercado Livre**.

---

## ✅ Funcionalidades Implementadas

### Catálogo Público (`index.html`)
- Listagem de produtos em grid responsivo
- **Seção de Destaques** (produtos com `featured: true`)
- **Filtro por loja**: Shopee, Amazon, Mercado Livre
- **Filtro por categoria** (dropdown populado dinamicamente)
- **Busca por nome/descrição/categoria**
- **Ordenação**: Mais recentes, Menor preço, Maior preço, Melhor avaliação
- **Paginação** completa
- **Modal de detalhe** de produto com rating, preço com desconto e botão de compra
- **Badge de loja** com cores oficiais em cada card
- **Badge de desconto** calculado automaticamente
- Links de afiliado com abertura em nova aba (`noopener, noreferrer`)
- Design responsivo (mobile-first)

### Painel de Administração (`admin.html`)
- **Estatísticas**: total de produtos, destaques, lojas ativas
- **Formulário completo** para adicionar/editar produto
- **Preview de imagem** ao colar a URL
- **Seleção de loja** com radio buttons visuais
- **Sugestões de categoria** via datalist
- **Listagem de produtos** com busca
- **Edição inline** (click em ✏️ preenche o formulário)
- **Exclusão com confirmação** via modal
- Notificações toast de sucesso/erro

---

## 📁 Estrutura de Arquivos

```
index.html          → Catálogo público
admin.html          → Painel de gerenciamento
css/
  style.css         → Todos os estilos (catálogo + admin)
js/
  main.js           → Lógica do catálogo público
  admin.js          → Lógica do painel admin
```

---

## 🔗 URIs / Rotas

| Página | Caminho |
|--------|---------|
| Catálogo público | `/index.html` |
| Admin — Gerenciar produtos | `/admin.html` |

---

## 🗄️ Modelo de Dados — Tabela `products`

| Campo | Tipo | Descrição |
|-------|------|-----------|
| `id` | text | ID único (UUID gerado automaticamente) |
| `name` | text | Nome do produto |
| `description` | rich_text | Descrição curta |
| `price` | number | Preço atual |
| `original_price` | number | Preço original (para cálculo do desconto) |
| `image_url` | text | URL da imagem do produto |
| `affiliate_link` | text | Link de afiliado para compra |
| `store` | text | `shopee`, `amazon` ou `mercadolivre` |
| `category` | text | Categoria livre (Eletrônicos, Moda...) |
| `rating` | number | Avaliação de 0 a 5 |
| `rating_count` | number | Número de avaliações |
| `featured` | bool | Se aparece na seção de Destaques |
| `active` | bool | Se está visível no catálogo |

---

## 🚀 API Utilizada (RESTful Table API)

| Operação | Endpoint |
|----------|----------|
| Listar produtos | `GET tables/products?limit=200` |
| Buscar produto | `GET tables/products/{id}` |
| Criar produto | `POST tables/products` |
| Atualizar produto | `PUT tables/products/{id}` |
| Excluir produto | `DELETE tables/products/{id}` |

---

## 🔜 Próximas Evoluções Sugeridas

- [ ] Sistema de login/proteção do painel admin
- [ ] Upload de imagem diretamente (não apenas URL)
- [ ] Analytics de cliques nos links de afiliado
- [ ] Página de produto individual com URL amigável
- [ ] Compartilhamento nas redes sociais (Open Graph)
- [ ] Filtro de preço por faixa (range slider)
- [ ] Modo escuro
- [ ] Integração com API de comparação de preços
- [ ] Newsletter / lista de favoritos

---

## 🛠️ Tecnologias Utilizadas

- HTML5 semântico
- CSS3 (variáveis, grid, flexbox, animações)
- JavaScript ES6+ (Fetch API, async/await)
- Font Awesome (ícones)
- Google Fonts — Inter
- RESTful Table API (banco de dados integrado)
