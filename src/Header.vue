<template>
    <nav class="navbar navbar-expand-lg navbar-dark bg-info">
      <router-link to="/">
        <a class="navbar-brand" href="#"><strong>Blogger</strong></a>
      </router-link>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item active">
            <router-link to="/editor">
              <a class="nav-link btn btn-success text-white" href="#"
              >New Blog<span class="sr-only">(current)</span></a>
            </router-link>
          </li>
        </ul>
        <form class="form-inline my-2 my-lg-0">
          <input
            class="form-control mr-sm-2"
            type="search"
            placeholder="Search"
            aria-label="Search"
          />
          <button class="btn btn-outline-dark my-2 my-sm-0" type="submit">
            Search
          </button>
        </form>
      </div>
    </nav>
</template>

<style scoped>
  a:hover {
    text-decoration: none;
  }
</style>
