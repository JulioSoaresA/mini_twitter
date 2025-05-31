# Diagrama de Entidade-Relacionamento (DER)

## Entidades e Relacionamentos

### Users
- **id**: Identificador único (PK)
- **username**: Nome de usuário (Unique)
- **email**: Email do usuário (Unique)
- **password**: Senha do usuário
- **created_at**: Data de criação

### Posts
- **id**: Identificador único (PK)
- **user_id**: Relacionamento com a tabela `Users` (FK)
- **content**: Conteúdo da postagem
- **created_at**: Data de criação

### Follows
- **id**: Identificador único (PK)
- **follower_id**: Usuário que segue (FK)
- **followed_id**: Usuário seguido (FK)

### Likes
- **id**: Identificador único (PK)
- **user_id**: Relacionamento com a tabela `Users` (FK)
- **post_id**: Relacionamento com a tabela `Posts` (FK)

## Relacionamentos
- **Users** possui um relacionamento 1:N com **Posts**.
- **Users** possui um relacionamento N:N com outros **Users** através de **Follows**.
- **Users** possui um relacionamento N:N com **Posts** através de **Likes**.

## Observações
- Todas as chaves estrangeiras possuem a regra `ON DELETE CASCADE` para garantir integridade referencial.
- Índices podem ser adicionados para otimizar consultas frequentes, como em `username`, `email`, e `created_at`. 
