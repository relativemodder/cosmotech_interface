<script>
    import "$lib/styles/forms.css";
    import { goto } from "$app/navigation"
    import Swal from 'sweetalert2';
                /*
            <input class="form-input" type="text" name="about" placeholder="Обращение клиента" required>
            <input class="form-input" type="text" name="master" placeholder="Выбор специалиста" required>
                */

    let isAddingClient = false;
</script>

<div class="middle">
    <div>
        <center>
            <h1>Клиенты</h1>
            <ul>
                <li>Кезин Андрей Денисович</li>
            </ul>
        </center>
        { #if !isAddingClient }
        <center>
            <button on:click={() => {isAddingClient = true}}>Добавить клиента</button>
        </center>
        { :else }
        <form on:submit|preventDefault={
            () => {
                Swal.fire({
                    title: "Успешно!",
                    text: "Клиент записан!",
                    icon: 'success'
                }).then(() => {
                    goto('/dashboard')
                })
            }
        }>
            <h2>Добавление клиента</h2>
            <input class="form-input" type="text" name="fullname" placeholder="ФИО" required>
            <input class="form-input" type="phone" name="phone" placeholder="Телефон" required>
            <input class="form-input" type="submit" value="Записать">
        </form>
        { /if }
    </div>
</div>