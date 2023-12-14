<script>
    import "$lib/styles/forms.css";
</script>

<svelte:head>
    <title>Войти</title>
</svelte:head>

<div class="middle">
    <form action="/dashboard" method="post">
        <input class="form-input" name="username" type="text" placeholder="Имя пользователя" required />
        <input class="form-input" name="username" type="password" placeholder="Пароль" required />

        <input class="form-input" type="submit" value="Вход" />
    </form>
</div>
