<script type="ts">
    let currentIndex = 0
    const users = [
        {
            name: 'Tanya Sinclair',
            position: 'UX Engineer',
            text: "I’ve been interested in coding for a while but never taken the jump, until now. I couldn’t recommend this course enough. I’m now in the job of my dreams and so excited about the future. ",
            image: './images/image-tanya.jpg'
        },
        {
            name: 'John Tarkpor',
            position: 'Junior Front-end Developer',
            text: "If you want to lay the best foundation possible I’d recommend taking this course. The depth the instructors go into is incredible. I now feel so confident about starting up as a professional developer. ",
            image: './images/image-john.jpg'

        }
    ]

    const nextUser = () => {
        currentIndex = (currentIndex + 1) % users.length;
    }
   
    const prevUser = () => {
        currentIndex = (currentIndex - 1 + users.length) % users.length;
    }
</script>

<div class="container">
    <div class="image-container">
        <img src={users[currentIndex].image} class="user-image" alt="user">
        <div class="btn-container">
            <button on:click={nextUser} class="btn-1">
                <img src="./images/icon-prev.svg" alt="prev">
            </button>
            <button on:click={prevUser} class="btn-2">
                <img src="./images/icon-next.svg" alt="next">
            </button>
        </div>
    </div>
    <div class="text-container">
        <div class="text-container-inner">
            <img src="./images/pattern-quotes.svg" class="quotes-image" alt="quotes">
            <p class="text">"{users[currentIndex].text}"</p>
            <div class="details-container">
                <p class="name">{users[currentIndex].name}</p>
                <p class="position">{users[currentIndex].position}</p>
            </div>
        </div>
        <img src="./images/pattern-curve.svg" class="footer-image" alt="footer">
    </div>
</div>

<style>
    .container {
		width: 23.438rem;
		background-color: #ffffff;
		display: block;
		margin-left: auto;
		margin-right: auto;
        font-family: "Inter", sans-serif;
        font-weight: 300;
        line-height: 1.5rem;
	}

    .image-container,
    .text-container{
        display: flex;
        flex-direction: column;
    }

    .image-container{
        background-image: url('./images/pattern-bg.svg');
        background-repeat: no-repeat;
        background-position: center;
        background-size: contain;
    }

    .user-image {
        width: 254px;
        margin: 0 auto;
        position: relative;
        top: 25px;
    }

    .btn-container{
        display: flex;
        justify-content: center;
        z-index: 1000;
    }

    button{
        border: none;
        border-radius: 28px;
        cursor: pointer;
    }

    .btn-1{
        border-radius: 28px 0 0 28px;
        padding: 14px 14px 14px 24px;
    }

    .btn-2{
        border-radius: 0 28px 28px 0;
        padding: 14px 24px 14px 14px;
    }

    .text-container{
        text-align: center;
    }
    
    .text-container-inner{
        margin-inline: 2rem;
    }

    .quotes-image{
        height: 50px;
        position: relative;
        top: 50px;
    }

    .name{
        font-weight: bold;
    }

    .position{
        color: #B9B9CE;
    }

    @media only screen and (min-width: 1200px){
        .container{
            display: flex;
            flex-direction: row-reverse;
            width: 74rem;
        }

        .image-container{
           flex: 1;
        }

        .btn-container{
            position: relative;
            top: 75px;
            right: 100px;
        }

        .text-container{
            flex: 1;
        }

        .user-image {
            position: relative;
            top: 100px;
            height: 475px;
            width: 475px;
        }

        .text-container-inner{
            position: relative;
            left: 75px;
        }

        .quotes-image{
            height: 100px;
            right: 125px;
            top: 75px;
        }

        .text{
            font-size: 32px;
            line-height: 44px;
        }

        .details-container{
            display: flex;
            align-items: center;
            font-size: 20px;
            gap: 10px;
        }

        .footer-image{
            height: 153px;
        }
    }
</style>