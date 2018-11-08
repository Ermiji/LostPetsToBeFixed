# Lost Pets

Contains some errors for you to fix!

It may not run completely, You should modify it to contain a link on the login page for a new user to register. And also allow a logged in user to edit their profile.

Example of a base.html file with a navbar and a footer. Call it to display the navbar as follows:

<div th:replace="base :: nav"></div>

Notice the yellow highlight which shows how the Username will display if the user is authenticated (logged in) otherwise the link to login will show.

You can view the entire lost pets project on GitHub at https://github.com/JBCSep2018/LostPetsToBeFixed (Links to an external site.)Links to an external site.

It may not run completely, You should modify it to contain a link on the login page for a new user to register. And also allow a logged in user to edit their profile.

Example of a base.html file with a navbar and a footer. Call it to display the navbar as follows:

<div th:replace="base :: nav"></div>


<!DOCTYPE html>
<html lang="en" xmlns:th="www.thymeleaf.org" xmlns:sec="http://www.w3.org/1999/xhtml">
<head th:fragment="header">
    <meta charset="UTF-8"/>
    <link th:href="@{/css/bootstrap.min.css}" rel="stylesheet" />
    <link th:href="@{/css/style.css}" rel="stylesheet"/>
</head>
<body>

<div th:fragment="nav">

    <nav class="navbar navbar navbar-expand-lg navbar-light bg-dark" th:fragment="main-navbar">
        <a class="navbar-brand text-white" href="/">
            &nbsp;FidoMissing
        </a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <!--</nav>-->
            <ul class="nav navbar-nav ml-auto">
                <li sec:authorize="isAuthenticated()" class="nav-link text-warning" th:inline="text">
                    Welcome [[${#authentication.name}]]!
                </li>
                <li class="nav-item">
                    <a sec:authorize="!isAuthenticated()" class="nav-link text-white" href="/login">Login</a>
                </li>
                <li class="nav-item text-light">
                    <a class="nav-link text-white" href="/">Home</a>
                </li>

                <li sec:authorize="isAuthenticated()" class="nav-item text-light">
                    <a class="nav-link text-white" href="/add">Missing Pet</a>
                </li>

                <li class="nav-item">
                    <a sec:authorize="isAuthenticated()" class="nav-link text-white"        href="/logout">Logout</a>
                </li>
            </ul>
        </div>
    </nav>

    <div class="space"></div>

    <div class="jumbotron text-center">
        <!--<h1>Fido is Missing! &#9785;</h1>-->
        <h1>Fido is Missing! &#9785;</h1>
    </div>

    <div class="space"></div>

</div>
  
    <footer th:fragment="footer">
        <div class="footer" align="center">
            <hr/>
            <span class="text-muted">&copy; 2018 Josemy Joseph</span>
        </div>
    </footer>

    <div th:fragment="scripts">
        <script src="/js/jquery.3.2.1.min.js"></script>
        <script src="/js/bootstrap.min.js"></script>
        <script src="/js/popper.min.js"></script>
    </div>

</div>
</body>
</html>

