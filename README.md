# navagation-menu-CSS
navagation-menu CSS

$color-white: #ffffff;
$color-black: #252a32;
$color-light: #f1f5f8;
$color-red: #d32f2f;
$color-blue: #148cb8;

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  list-style: none;
  text-decoration: none;
  -moz-osx-font-smoothing: grayscale;
	-webkit-font-smoothing: antialiased;
	text-rendering: optimizeLegibility;
}

body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  font-size: 1rem;
  font-weight: normal;
  line-height: 1.5;
  color: $color-black;
  background: $color-white;
}

.hidden {
  display: none;
}

.header {
  width: 100%;
  height: 100vh;
  background: url(https://bit.ly/2QNWUBq);
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;

  .navbar {
    display: flex;
    flex-direction: row;
    flex: 1;
    flex-basis: auto;
    justify-content: space-between;
    align-items: center;
    max-width: 90rem;
    width: 100%;
    padding: 1rem 4rem;
    margin: 0 auto;

    .brand {
      font-family: inherit;
      font-size: 1.75rem;
      font-weight: 700;
      line-height: inherit;
      text-transform: uppercase;
      color: $color-black;
    }

    .menu {
      display: flex;
      flex-direction: row;
      flex: 1;
      flex-basis: auto;
      justify-content: center;
      align-items: center;

      &-item {
        &:not(:first-child) {
          margin-left: 2rem;
        }

        a {
          font-family: inherit;
          font-size: 1rem;
          font-weight: 700;
          line-height: inherit;
          color: $color-black;
          text-transform: uppercase;
        }
      }
    }
  }
}

@media only screen and (max-width: 768px) {
  .header {
    .navbar {
      padding: 1rem 2rem;
      margin: 0 auto;
      
      .wrapper {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: -1;
        opacity: 0;
        background: $color-light;
        transition: all 0.3s ease;

        .menu {
          display: flex;
          flex-direction: column;
          position: absolute;
          top: 25%;
          width: 100%;
          transform: translateY(-50%);

          &-item {
            padding-bottom: 1rem;
            width: 100%;
            text-align: left;

            &:nth-child(1) a {
              transition-delay: 0.2s;
            }
            &:nth-child(2) a {
              transition-delay: 0.3s;
            }
            &:nth-child(3) a {
              transition-delay: 0.4s;
            }
            &:nth-child(4) a {
              transition-delay: 0.5s;
            }

            &:not(:first-child) {
              margin-left: 0;
            }

            a {
              padding: 1rem 2rem;
              opacity: 0;
              color: $color-black;
              font-size: 1rem;
              font-weight: 600;
              transform: translateX(-20px);
              transition: all 0.3s ease-in-out;
            }
          }
        }
      }

      .nav-toggle {
        display: block;
        position: fixed;
        right: 1rem;
        top: 1rem;
        width: 2.5rem;
        height: 2.5rem;
        cursor: pointer;
        z-index: 999;

        span {
          display: block;
          width: 20px;
          height: 2px;
          background: $color-black;
          border-radius: 2px;
          margin-left: 14px;

          &:nth-child(1) {
            margin-top: 16px;
          }
          &:nth-child(2) {
            margin-top: 4px;
            opacity: 1;
          }
          &:nth-child(3) {
            margin-top: 4px;
          }
        }
      }

      #nav:checked + .nav-toggle {
        transform: rotate(45deg);

        span {
          background: $color-black;
          transition: transform 0.5s ease;

          &:nth-child(1) {
            transform: translateY(6px) rotate(180deg);
          }
          &:nth-child(2) {
            opacity: 0;
          }
          &:nth-child(3) {
            transform: translateY(-6px) rotate(90deg);
          }
        }
      }

      #nav:checked ~ .wrapper {
        z-index: 99;
        opacity: 1;

        .menu {
          &-item {
            a {
              opacity: 1;
              transform: translateX(0);
            }
          }
        }
      }
    }
  }
}

