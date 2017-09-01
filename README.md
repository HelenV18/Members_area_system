# Members_area_system
Create a user account system in PHP part 1


<br><br>


<p>Create a procedural PHP member system. Our system will consist of the following features:</p>
<ul>
    <li>One part registration with confirmation by email</li>
    <li>A connection / disconnection part, with a "Remember me" option</li>
    <li>A system of recall and modification of password</li>
    <li>A member-only page</li>
</ul>




<br><br>




<h3>1 - The basic structure of our member space:</h3>

<ul>
    <li>Folder css: contains all our css</li>      
    <li>Inc folder: contains all files to include in our pages</li>       
    <ul>
        <li>header.php defines the header of our pages</li>
        <li>footer.php defines the footer of our pages</li>
        <li>functions.php: defines all functions of the site</li>
    </ul>
</ul>
<ul>
    <li>At the root of the site:</li>
    <ul>
        <li>register.php: allows the user to register</li>    
    </ul>
</ul>




<br><br>




<h3>2 - User Registration :</h3>

<p>
    The registration part allows users to create an account.
    You end up with a standard form that generates errors if the fields are not filled in properly
</p>

<br>

<p>Handling Form Error Messages : </p>
<pre>
    if(empty($_POST['username']) || !preg_match('/^[a-zA-Z0-9_]+$/', $_POST['username'])){
        $errors['username'] = "Votre pseudo n'est pas valide";
    }

    if(empty($_POST['email']) || !filter_var($_POST['email'], FILTER_VALIDATE_EMAIL)){
        $errors['email'] = "Votre email n'est pas valide";
    }


    if(empty($_POST['password']) || $_POST['password'] != $_POST['password_confirm']){
        $errors['password'] = "Votre mot de passe n'est pas valide";
    }
</pre>
