# Diagrama Entidade-Relacionamento (ERD)

## Entidades

### Usuários
- `id`: Identificador único (Primary Key).
- `username`: Nome de usuário (Unique).
- `email`: Endereço de e-mail (Unique).
- `password`: Senha do usuário.
- `created_at`: Data e hora de criação do registro.

### Posts
- `id`: Identificador único (Primary Key).
- `user_id`: Identificador do usuário que criou o post (Foreign Key para Usuários).
- `content`: Conteúdo do post (Texto).
- `created_at`: Data e hora de criação do post.

### Seguidores/Relações
- `id`: Identificador único (Primary Key).
- `follower_id`: Identificador do usuário que segue (Foreign Key para Usuários).
- `followed_id`: Identificador do usuário seguido (Foreign Key para Usuários).
- `created_at`: Data e hora de criação da relação.

## Relacionamentos

### Usuários e Posts
- Relacionamento 1:N (Um usuário pode criar vários posts).

### Usuários e Seguidores/Relações
- Relacionamento N:N (Um usuário pode seguir e ser seguido por vários outros usuários).

## Visualização em Markdown

```plaintext
[Usuários]
+ id (PK)
+ username (Unique)
+ email (Unique)
+ password
+ created_at

[Posts]
+ id (PK)
+ user_id (FK -> Usuários.id)
+ content
+ created_at

[Seguidores/Relações]
+ id (PK)
+ follower_id (FK -> Usuários.id)
+ followed_id (FK -> Usuários.id)
+ created_at
```
