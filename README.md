````
const Auth = {
  login: (token, userData) => {
    localStorage.setItem("accessToken", token);
    localStorage.setItem("MERCHANT_DATA", JSON.stringify(userData));
  },

  logout: () => {
    localStorage.removeItem("accessToken");
    localStorage.removeItem("MERCHANT_DATA");
    window.location.href = "/login";
  },

  getRole: () => {
    const data = JSON.parse(localStorage.getItem("MERCHANT_DATA"));
    return data?.role?.toUpperCase() || null;
  },

  getAccessToken: () => {
    return localStorage.getItem("accessToken");
  },

  getUser: () => {
    return JSON.parse(localStorage.getItem("MERCHANT_DATA")) || null;
  },
};
````

export default Auth;
