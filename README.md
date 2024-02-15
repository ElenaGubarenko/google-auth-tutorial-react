# google-auth-tutorial
Quick google auth tutorial

1. Install @react-oauth/google
2. Auth component:
3. Component:
<pre><code class="language-js">
import React from "react";
import { useGoogleLogin } from '@react-oauth/google';

const Google = ({ }) => {
  const { registerUser, logInUser } = useAuth();

  const googleButStyle = {
    backgroundColor: '#4267b2',
    display: 'flex',
    alignItems: 'center',
    justifyContent: 'center',
    color: '#fff',
    fontSize: '1em',
    windth: `1em`,
    height: `1em`,
    padding: '1em',
    border: 'none',
    borderRadius: '50%',
  };

  const googleLogin = useGoogleLogin({
    onSuccess: (tokenResponse) => {
      console.log('Google login successful', tokenResponse);
    },
    onError: () => {
      console.error('Google login failed');
    },
    flow: 'auth-code',
  });

  return (
    <button
      style={googleButStyle}
      onClick={() => googleLogin()}>
      g
    </button>
  );
};

export default Google; 
</code>
</pre>
4. Don't forget:
 <pre>
 <code class="language-js">
   import { GoogleOAuthProvider } from '@react-oauth/google';
   ...
   < GoogleOAuthProvider clientId="CLIENT_ID.apps.googleusercontent.com">
     {children}
   < /GoogleOAuthProvider>);
</code>
</pre>
6. Go to `google console`
7. Here you can create your client ID: 
 ![image](https://github.com/ElenaGubarenko/google-auth-tutorial-react/assets/61194378/ca4c6255-9658-41b1-bb58-d8f4b0229745)
8. Register your site:
 ![image](https://github.com/ElenaGubarenko/google-auth-tutorial-react/assets/61194378/c75fb793-520c-4283-a91c-85a7ad781f6d)
9. Thats all! 🐱‍👤




