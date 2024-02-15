# google-auth-tutorial
Quick google auth tutorial

1. Install @react-oauth/google
2. Auth component: 
import React from "react";
import { useGoogleLogin } from '@react-oauth/google';

const Google = ({ }) => {
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
