<script>
    import "$lib/styles/forms.css";
    import { goto } from "$app/navigation"
    import Swal from 'sweetalert2';

    let isAddingOrder = false;
</script>

<div class="middle">
    <div>
        <center>
            <h1>Заказы</h1>
            <ul>
                <li>Кезин А.Д. - Пластика - к Трофимову А.Д. </li>
            </ul>
        </center>
        { #if !isAddingOrder }
        <center>
            <button on:click={() => {isAddingOrder = true}}>Добавить заказ</button>
        </center>
        { :else }
        <form on:submit|preventDefault={
            () => {
                Swal.fire({
                    title: "Успешно!",
                    text: "Заказ записан!",
                    icon: 'success'
                }).then(() => {
                    goto('/dashboard')
                })
            }
        }>
            <h2>Добавление заказа</h2>
            <input class="form-input" type="text" name="fullname" placeholder="ФИО Клиента" required>
            <input class="form-input" type="text" name="about" placeholder="Обращение клиента" required>
            <input class="form-input" type="text" name="master" placeholder="Выбор специалиста" required>
            <input class="form-input" type="submit" value="Записать">
        </form>
        { /if }
    </div>
</div>