<script>
    import logo from '$lib/assets/Logo.png';
</script>

<nav>
    <div class='logo'>
        <img src={logo} alt="" >
        <p>projectDesign</p>
    </div>
    <ul>
        <li class="home nav-items"><a href="/">Home</a></li>
        <li class='divider1 divider'>|</li>
        <li class="projects nav-items"><a href="/projects">Projects</a></li>
        <li class="divider2 divider">|</li>
        <li class="services nav-items"><a href="/services">Services</a></li>
        <li class="divider3 divider">|</li>
        <li class="contact nav-items"><a href="/contact">Contact</a></li>
    </ul>
</nav>

<style>
    nav{
        display: flex;
        justify-content: space-between;
        padding-block: 10px;
        padding-inline: 30px;

        .logo {
            align-items: center;
            background-color: aliceblue;
            display: flex;
            padding-block: 5px;
            padding-inline: 10px;
            border-radius: 10px;

            img {
                height: 50px;
                width: 50px;
            }
            p {
                color: rgb(101, 164, 201);
                font-size: 30px;
                margin-left: 0px;
                margin: 0px;
                opacity: 0;
                padding: 0px;
                transition: all 0.8s ease;
                visibility: hidden;
                width: 0px;
            }
        }
        .logo:hover {
            p {
                margin-left: 10px;
                opacity: 1;
                visibility: visible;
                width: auto;
            }
        }

        ul {
            background-color: aliceblue;
            border-radius: 10px;
            display: flex;
            gap: 40px;
            list-style: none;
            margin: 10px;
            padding-block: 15px;
            padding-inline: 30px;

            li {
                margin-block: auto;
                text-align: center;
                width: max-content;
                transition: all 0.8s ease;
            }

            .divider {
                opacity: 0;
                width: 0px;
            }

            .nav-items:hover {
                padding-inline: 15px;
            }

            .home:hover ~ .divider1 { 
                opacity: 1;
                width: auto;
            }
            .projects:hover ~ .divider1, .projects:hover ~ .divider2 {
                opacity: 1;
                width: auto;
            }
            .services:hover ~ .divider2, .services:hover ~ .divider3 {
                opacity: 1;
                width: auto;
            }
            .contact:hover ~ .divider3 { 
                opacity: 1;
                width: auto;
            }
        }
    }
</style>
