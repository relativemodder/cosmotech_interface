<script>
    import { goto } from "$app/navigation";
</script>

<div class="navbar">
    <button on:click={() => goto("/dashboard")}>Аккаунт</button>
    <button on:click={() => goto("/dashboard/clients")}>Клиенты</button>
    <button on:click={() => goto("/dashboard/staff")}>Сотрудники</button>
    <button on:click={() => goto("/dashboard/orders")}>Заказы</button>
</div>

<style>
    .navbar {
        position: fixed;
        top: 0px;
        left: 0px;
        width: 100%;
        min-height: 32px;
        box-shadow: #00000036 0px 1px 20px 0px;
        padding: 30px;
        display: flex;
        gap: 40px;
    }
    button {
        font-size: larger;
        background-color: none;
        border: none;
    }
</style>