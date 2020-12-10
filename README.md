# optionValue-months
little on css and js
<style>
    div {
        height: 200px;
        width: 500px;
        align-content: center;
        background-color: blue;
    }
    
    p {
        color: white;
    }
    
    body {
        width: 200vw;
        height: 200vw;
        margin: 0;
    }
    
    label {
        border-left: 58px;
        margin-left: 50px;
        width: 20px;
        height: 20px;
        color: white;
        font-size: large;
    }
    
    input {
        border-left: 80px;
        width: 70px;
        height: 20px;
        background-color: gray;
    }
    
    #btn {
        border-top: 40px;
        width: 70px;
        height: 40px;
    }
</style>

<body>
    <div>
        <label for="search">search contact: </label>
        <input type="text" id="search">

        <button id="btn"> search</button>
        <p></p>
    </div>
    <script>
        const contacts = ["Abby:3gdhu28839", "Mills: 588y9hik", "Jeremy: 5itk0040", "Bill:9587y", "Carter Jones: 39585"];
        const input = document.querySelector("input");
        const button = document.querySelector("button");
        const para = document.querySelector("p");
        button.addEventListener("click", function() {
            const inputVal = input.value;
            let searches = input.value.toLowerCase();
            input.focus();

            for (let i = 0; i < contacts.length; i++) {
                let sieve = contacts[i].split(":");
                let name = sieve[0];
                let number = sieve[1];
                if (inputVal.length === 0) {
                    para.textContent = "Please enter a number";
                } else if (name.toLowerCase() === searches) {
                    para.textContent = name + "'s number is" + number;
                    break;

                } else {
                    para.textContent = "Contact not found";


                }
            }
        })
