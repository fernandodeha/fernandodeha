import React, { useState } from "react";
import { Facebook } from "lucide-react";
export function App() {
  const [showPassword, setShowPassword] = useState(false);
  const [username, setUsername] = useState("");
  const [password, setPassword] = useState("");
  return (
    <div className="flex flex-col items-center justify-center min-h-screen bg-gray-50 px-4">
      <div className="w-full max-w-sm">
        <div className="bg-white p-8 border border-gray-300 mb-4 flex flex-col items-center">
          <img
            src="https://www.instagram.com/static/images/web/mobile_nav_type_logo.png/735145cfe0a4.png"
            alt="Instagram"
            className="mb-8 h-12"
          />
          <form className="w-full">
            <div className="mb-2">
              <div className="relative">
                <input
                  type="text"
                  className={`w-full px-2 py-2 text-xs border ${username ? "border-gray-300" : "border-gray-200"} rounded bg-gray-50 focus:outline-none`}
                  placeholder="Phone number, username, or email"
                  value={username}
                  onChange={(e) => setUsername(e.target.value)}
                />
              </div>
            </div>
            <div className="mb-4">
              <div className="relative">
                <input
                  type={showPassword ? "text" : "password"}
                  className={`w-full px-2 py-2 text-xs border ${password ? "border-gray-300" : "border-gray-200"} rounded bg-gray-50 focus:outline-none`}
                  placeholder="Password"
                  value={password}
                  onChange={(e) => setPassword(e.target.value)}
                />
                {password && (
                  <button
                    type="button"
                    className="absolute right-2 top-1/2 transform -translate-y-1/2 text-sm font-semibold"
                    onClick={() => setShowPassword(!showPassword)}
                  >
                    {showPassword ? "Hide" : "Show"}
                  </button>
                )}
              </div>
            </div>
            <button
              type="submit"
              className={`w-full py-1 rounded text-sm font-medium ${username && password ? "bg-blue-500 text-white" : "bg-blue-300 text-white cursor-not-allowed"}`}
              disabled={!username || !password}
            >
              Log In
            </button>
          </form>
          <div className="flex items-center w-full my-4">
            <div className="flex-1 h-px bg-gray-300"></div>
            <div className="px-4 text-sm font-semibold text-gray-500">OR</div>
            <div className="flex-1 h-px bg-gray-300"></div>
          </div>
          <button className="flex items-center justify-center text-sm font-semibold text-blue-900 mb-4">
            <Facebook size={16} className="mr-2 text-blue-900" />
            Log in with Facebook
          </button>
          <a href="#" className="text-xs text-blue-900 mb-4">
            Forgot password?
          </a>
        </div>
        <div className="bg-white p-6 border border-gray-300 text-center">
          <p className="text-sm">
            Don't have an account?{" "}
            <a href="#" className="text-blue-500 font-semibold">
              Sign up
            </a>
          </p>
        </div>
        <div className="mt-4 text-center">
          <p className="text-sm mb-4">Get the app.</p>
          <div className="flex justify-center space-x-2">
            <a href="#" className="block">
              <img
                src="https://www.instagram.com/static/images/appstore-install-badges/badge_ios_english-en.png/180ae7a0bcf7.png"
                alt="Download on App Store"
                className="h-10"
              />
            </a>
            <a href="#" className="block">
              <img
                src="https://www.instagram.com/static/images/appstore-install-badges/badge_android_english-en.png/e9cd846dc748.png"
                alt="Get it on Google Play"
                className="h-10"
              />
            </a>
          </div>
        </div>
      </div>
      <div className="mt-6 text-center text-xs text-gray-500">
        <div className="flex flex-wrap justify-center gap-x-4 gap-y-2 mb-4">
          <a href="#">Meta</a>
          <a href="#">About</a>
          <a href="#">Blog</a>
          <a href="#">Jobs</a>
          <a href="#">Help</a>
          <a href="#">API</a>
          <a href="#">Privacy</a>
          <a href="#">Terms</a>
          <a href="#">Top Accounts</a>
          <a href="#">Locations</a>
          <a href="#">Instagram Lite</a>
        </div>
        <div>© 2023 Instagram from Meta</div>
      </div>
    </div>
  );
}
