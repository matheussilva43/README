# SWR CLOUD - Gestor Web

Sistema de modulado.

### Pré-requisitos


O que você precisa para instalar o software e instalá-lo

```
PHP: >=7.0.0,
```

### Instalando

Passo a passo

Dar um git clone do projeto
```
1. Faça o clone deste projeto com `git clone https://matheussilva43@bitbucket.org/suportware/gestorweb.git`
2. No arquivo .env.example duplique e renomei para .env
3. Comentar as linas de códigos no arquivo app/Providers/AuthServiceProvider.php, linhas 34 a 41.
```
```
        $this->registerPolicies($gate);
        $permissions = Permission::with('roles')->get();

        foreach ($permissions as $permission) {
            $gate->define($permission->name, function (User $user) use ($permission) {
                return $user->hasPermission($permission);
            });
        }
```
```
4. Entre na pasta do projeto e instale as dependências com 
    `composer update`
    `composer dumpautoload`
    `php artisan migrate --seed`
```
```
5. Rode a aplicação com `php artisan serve`
```

## Testando a aplicação

1. Abra o browser e visite a página http://localhost:8000
