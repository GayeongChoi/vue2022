<template>
  <div>
    <header id="header">
      <div className="header__port">
        <router-link to="/port">portfolio</router-link>
      </div>
      <div className="header__logo">
        <router-link to="/">GayeongChoi</router-link>
      </div>
      <nav className="header__menu">
        <ul>
          <li>
            <router-link to="/about">About</router-link>
          </li>
          <li>
            <router-link to="/refer">Reference</router-link>
          </li>
          <li>
            <router-link to="/youtube">Youtube</router-link>
          </li>
          <li>
            <router-link to="/movie">Movie</router-link>
          </li>
          <li>
            <router-link to="/contact">Contact</router-link>
          </li>
        </ul>
      </nav>
    </header>
  </div>
</template>

<style lang="scss">
#header {
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  color: var(--white);
  border-bottom: 1px solid var(--dark_border);
  background-color: var(--dark_bg);
  display: flex;
  align-items: center;
  font-family: "Rajdhani";
  z-index: 1000;
}
.header__port {
  flex: 1 1 40%;

  a {
    display: inline-block;
    padding: 0 1rem;
    text-transform: capitalize;
    border-right: 1px solid var(--dark_border);
    position: relative;

    &::before {
      content: "";
      position: absolute;
      left: 0;
      bottom: -3px;
      width: 100%;
      height: 1px;
      background: var(--white);

      transform: scaleX(0);
      transition: all 0.3s ease;
    }
    &:hover:before {
      transform: scaleX(1);
    }
  }
}
.header__logo {
  flex: 1 1 20%;
  text-align: center;

  a {
    display: inline-block;
    font-size: 1.6rem;
    padding: 1rem; //16px정도 된다.s
  }
}
.header__menu {
  flex: 1 1 40%;
  text-align: right;

  li {
    display: inline;
    position: relative;

    a {
      display: inline-block;
      padding: 1rem; //16px정도 된다.

      &::before {
        content: "";
        position: absolute;
        left: 0;
        bottom: -3px;
        width: 100%;
        height: 1px;
        background: #fff;
        transform: scaleX(0);
        transition: all 0.3s ease;
      }
      &:hover:before {
        transform: scaleX(1);
      }
    }
  }
}

//라이트 버전
.light#header {
  background-color: var(--light_bg);
  border-color: var(--light_border);

  a {
    color: var(--black);

    &::before {
      background: var(--black);
    }
  }
}

//미디어 쿼리
@media (max-width: 1300px) {
  .header__menu {
    display: none;
  }
  .header__port {
    display: none;
  }
}
@media (max-width: 600px) {
  #header {
    background: rbga(0, 0, 0, 0.1);
    backdrop-filter: blur(40px);
    border-bottom-color: #c2c2c2;
  }
}
</style>
