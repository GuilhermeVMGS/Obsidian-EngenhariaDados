### 1. Administrador (Admin)

- Pode adicionar ou remover qualquer pessoa do Workspace (inclusive outros Admins).
- Pode excluir ou alterar as configurações do Workspace.
- Tem controle total sobre relatórios, painéis e modelos semânticos.

### 2. Membro (Member)

- Pode adicionar outros usuários com permissões de Membro, Colaborador ou Visualizador.
- Pode publicar, editar e atualizar Aplicativos (Apps) do Workspace.
- Pode criar e editar conteúdos no espaço de trabalho.    

### 3. Colaborador (Contributor)

- Pode criar, editar e excluir relatórios e painéis dentro do Workspace.
- Pode agendar atualizações de dados.
- **Não pode** alterar permissões de usuários nem publicar/atualizar o Aplicativo do Workspace.

### 4. Visualizador (Viewer)

- Possui acesso apenas de leitura aos relatórios e painéis.
- Pode interagir com os visuais (filtrar, fatiar e exportar dados).
- É a **única função** que é impactada pelas regras de Segurança em Nível de Linha (RLS - Row-Level Security). As outras funções (Admin, Membro e Colaborador) editam o modelo e por isso ignoram as regras de RLS.