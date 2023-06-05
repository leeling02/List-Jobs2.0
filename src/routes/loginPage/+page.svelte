<script>
    import { authenticateUser } from "../../utils/auth";
    import { goto } from '$app/navigation';

  
    function postLogin() {
        goto('/jobs/new');
      }
    
      //Sections below are as --Login Function--
      async function Login() {
        //Keyin username and password for log in 
        const userData = {
          username: evt.target['username'].value,        
          password: evt.target['password'].value,
        };
  
        console.log("123")
        authenticateUser(userData.username, userData.password)
      
      //to track whether he/she is authenticated user, using authenticated function
  
        if (res.success) {
          postLogin();
      //Unhappy path 
        } else {
          throw 'Please check your username/password';
        
        }
  
      }
  
    
  
      
    
  
  
  </script>
  
  
  <div>
  
  <form on:submit={Login}>
    <label style="display:flex; flex-direction:column; align-items:center; justify-content: center">
      Username:
      <input type="text" name="username" required>
    </label >
    <label style="display:flex; flex-direction:column; align-items:center; justify-content: center">
      Password:
      <input type="password" name="password" required>
    </label>
  
    <button  id="loginButton" style="position:absolute; right: 700px">Log in</button>
    
  </form>
  
  </div>
    
  
      
  
      