<script>
    import "$lib/styles/forms.css";
    import { goto } from "$app/navigation"
    import Swal from 'sweetalert2';

    let isAddingStaff = false;
</script>

<div class="middle">
    <div>
        <center>
            <h1>Сотрудники</h1>
            <ul>
                <li>Трофимов Артём Денисович</li>
            </ul>
        </center>
        { #if !isAddingStaff }
        <center>
            <button on:click={() => {isAddingStaff = true}}>Добавить сотрудника</button>
        </center>
        { :else }
        <form on:submit|preventDefault={
            () => {
                Swal.fire({
                    title: "Успешно!",
                    text: "Сотрудник записан!",
                    icon: 'success'
                }).then(() => {
                    goto('/dashboard')
                })
            }
        }>
            <h2>Добавление сотрудника</h2>
            <input class="form-input" type="text" name="fullname" placeholder="ФИО" required>
            <input class="form-input" type="phone" name="phone" placeholder="Телефон" required>
            <input class="form-input" type="text" name="address" placeholder="Адрес" required>
            <input class="form-input" type="text" name="position" placeholder="Должность" required>
            <input class="form-input" type="submit" value="Записать">
        </form>
        { /if }
    </div>
</div>