<template>
  <header class="nhsuk-header nhsuk-header--transactional" role="banner">
    <div class="nhsuk-width-container nhsuk-header__container">
      <div class="nhsuk-header__logo nhsuk-header__logo--only">
        <a class="nhsuk-header__link" href="/" aria-label="NHS homepage">
          <svg
            class="nhsuk-logo logo-centre"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 40 16"
            height="40"
            width="100"
          >
            <path
              class="nhsuk-logo__background"
              fill="#005eb8"
              d="M0 0h40v16H0z"
            ></path>
            <path
              class="nhsuk-logo__text"
              fill="#fff"
              d="M3.9 1.5h4.4l2.6 9h.1l1.8-9h3.3l-2.8 13H9l-2.7-9h-.1l-1.8 9H1.1M17.3 1.5h3.6l-1 4.9h4L25 1.5h3.5l-2.7 13h-3.5l1.1-5.6h-4.1l-1.2 5.6h-3.4M37.7 4.4c-.7-.3-1.6-.6-2.9-.6-1.4 0-2.5.2-2.5 1.3 0 1.8 5.1 1.2 5.1 5.1 0 3.6-3.3 4.5-6.4 4.5-1.3 0-2.9-.3-4-.7l.8-2.7c.7.4 2.1.7 3.2.7s2.8-.2 2.8-1.5c0-2.1-5.1-1.3-5.1-5 0-3.4 2.9-4.4 5.8-4.4 1.6 0 3.1.2 4 .6"
            ></path>
          </svg>
        </a>
      </div>
      <div class="nhsuk-header__transactional-service-name logo-centre">
        <a class="nhsuk-header__transactional-service-name--link" href="#"
          >Prescription Tracker</a
        >
      </div>
      <div class="nhs-login-data">
        <p class="para bold">Jamie Carter</p>
        <p class="para parasmall"></p>

        <p class="para parasmall">Admin/Clinical Support Access Role - <b>Peak Pharmacy</b> </p>
      </div>
    </div>
    <nav
      class="nhsuk-header__navigation app-header__navigation"
      id="header-navigation"
      role="navigation"
      aria-label="Primary navigation"
      aria-labelledby="label-navigation"
    >
      <div class="nhsuk-width-container app-width-container">
        <p class="nhsuk-header__navigation-title">
          <span id="label-navigation">Menu</span>
          <button class="nhsuk-header__navigation-close" id="close-menu">
            <svg
              class="nhsuk-icon nhsuk-icon__close"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              aria-hidden="true"
              focusable="false"
            >
              <path
                d="M13.41 12l5.3-5.29a1 1 0 1 0-1.42-1.42L12 10.59l-5.29-5.3a1 1 0 0 0-1.42 1.42l5.3 5.29-5.3 5.29a1 1 0 0 0 0 1.42 1 1 0 0 0 1.42 0l5.29-5.3 5.29 5.3a1 1 0 0 0 1.42 0 1 1 0 0 0 0-1.42z"
              ></path>
            </svg>
            <span class="nhsuk-u-visually-hidden">Close menu</span>
          </button>
        </p>
        <ul class="nhsuk-header__navigation-list">
          <li
            class="
              nhsuk-header__navigation-item
              nhsuk-header__navigation-item--for-mobile
            "
          >
            <a class="nhsuk-header__navigation-link" href="/">
              Home
              <svg
                class="nhsuk-icon nhsuk-icon__chevron-right"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                aria-hidden="true"
                width="27"
                height="27"
              >
                <path
                  d="M15.5 12a1 1 0 0 1-.29.71l-5 5a1 1 0 0 1-1.42-1.42l4.3-4.29-4.3-4.29a1 1 0 0 1 1.42-1.42l5 5a1 1 0 0 1 .29.71z"
                ></path>
              </svg>
            </a>
          </li>

          <li class="nhsuk-header__navigation-item">
            <a class="nhsuk-header__navigation-link" href="/">
              Track A Presciption
              <svg
                class="nhsuk-icon nhsuk-icon__chevron-right"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                aria-hidden="true"
                width="34"
                height="34"
              >
                <path
                  d="M15.5 12a1 1 0 0 1-.29.71l-5 5a1 1 0 0 1-1.42-1.42l4.3-4.29-4.3-4.29a1 1 0 0 1 1.42-1.42l5 5a1 1 0 0 1 .29.71z"
                ></path>
              </svg>
            </a>
          </li>

          <li
            class="
              nhsuk-header__navigation-item
              app-header__navigation-item__item--current
            "
          >
            <a class="nhsuk-header__navigation-link" href="/design-system">
              Change Role
              <svg
                class="nhsuk-icon nhsuk-icon__chevron-right"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                aria-hidden="true"
                width="34"
                height="34"
              >
                <path
                  d="M15.5 12a1 1 0 0 1-.29.71l-5 5a1 1 0 0 1-1.42-1.42l4.3-4.29-4.3-4.29a1 1 0 0 1 1.42-1.42l5 5a1 1 0 0 1 .29.71z"
                ></path>
              </svg>
            </a>
          </li>

          <li class="nhsuk-header__navigation-item">
            <a class="nhsuk-header__navigation-link" href="/content">
              Change Mode
              <svg
                class="nhsuk-icon nhsuk-icon__chevron-right"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                aria-hidden="true"
                width="34"
                height="34"
              >
                <path
                  d="M15.5 12a1 1 0 0 1-.29.71l-5 5a1 1 0 0 1-1.42-1.42l4.3-4.29-4.3-4.29a1 1 0 0 1 1.42-1.42l5 5a1 1 0 0 1 .29.71z"
                ></path>
              </svg>
            </a>
          </li>

          <li class="nhsuk-header__navigation-item">
            <a class="nhsuk-header__navigation-link" href="/accessibility">
              Help
              <svg
                class="nhsuk-icon nhsuk-icon__chevron-right"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                aria-hidden="true"
                width="34"
                height="34"
              >
                <path
                  d="M15.5 12a1 1 0 0 1-.29.71l-5 5a1 1 0 0 1-1.42-1.42l4.3-4.29-4.3-4.29a1 1 0 0 1 1.42-1.42l5 5a1 1 0 0 1 .29.71z"
                ></path>
              </svg>
            </a>
          </li>

          <li class="nhsuk-header__navigation-item">
            <a
              class="nhsuk-header__navigation-link"
              href="/community-and-contribution"
            >
              Exit Tracker
              <svg
                class="nhsuk-icon nhsuk-icon__chevron-right"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                aria-hidden="true"
                width="34"
                height="34"
              >
                <path
                  d="M15.5 12a1 1 0 0 1-.29.71l-5 5a1 1 0 0 1-1.42-1.42l4.3-4.29-4.3-4.29a1 1 0 0 1 1.42-1.42l5 5a1 1 0 0 1 .29.71z"
                ></path>
              </svg>
            </a>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<style scoped>
.nhs-login-data {
  /* border: 3px solid rgb(255, 251, 0); */
  float: right;
  display: block;
  padding: 12px 18px;
  background: #ffeb3b;
  /* background: rgba(0, 0, 0, 0.1); */
}

.para {
  font-size: 20px;
  color: #212b32;
  margin-bottom: 0px;
  text-align: right;
}

.parasmall {
  font-size: 14px;
}

.bold {
  font-weight: 600;
}

.logo-centre {
  margin-top: 24px;
}

.split {
  display: flex;
  justify-content: space-between;
}
</style>
