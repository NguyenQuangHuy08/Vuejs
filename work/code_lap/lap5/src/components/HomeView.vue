<script setup>

defineProps({
    title: {
        type: String,
        required: true
    }

})

</script>
<template>
    <h1 class="" style="display: none;">{{ title }}</h1>
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
        <div class="container-fluid">
            <img src="" alt="">
            <a class="navbar-brand" href="#">Flowbite</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
                aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <a class="nav-link active" aria-current="page" href="#">Home</a>
                    </li>
                    <li class="nav-item dropdown">
                        <a style="color: black;font-weight: 400;" class="nav-link dropdown-toggle" href="#"
                            role="button" data-bs-toggle="dropdown" aria-expanded="false">
                            Comapany
                        </a>
                        <ul style="width: 400px;margin-right: 10px;" class="dropdown-menu">
                            <div class="row" style="">
                                <div class="col-3">
                                    <li><a class="dropdown-item" href="#">About US</a></li>
                                    <li><a class="dropdown-item" href="#">Libary</a></li>
                                    <li><a class="dropdown-item" href="#">Resources</a></li>
                                    <li><a class="dropdown-item" href="#">Pro version</a></li>
                                </div>
                                <div class="col-3">
                                    <li><a class="dropdown-item" href="#">Blog</a></li>
                                    <li><a class="dropdown-item" href="#">Newsletter</a></li>
                                    <li><a class="dropdown-item" href="#">Palyground</a></li>
                                    <li><a class="dropdown-item" href="#">License</a></li>
                                </div>
                                <div class="col-3">
                                    <li><a class="dropdown-item" href="#">Contact US</a></li>
                                    <li><a class="dropdown-item" href="#">Support Center</a></li>
                                    <li><a class="dropdown-item" href="#">Tearm</a></li>
                                </div>
                            </div>
                        </ul>
                    </li>
                    <li class="nav-item">
                        <a style="color: black;font-weight: 400;" class="nav-link" href="#">Team</a>
                    </li>
                    <li class="nav-item">
                        <a style="color: black;font-weight: 400;" class="nav-link" aria-disabled="true">Contact</a>
                    </li>
                </ul>
                <div class="row">
                    <div class="col-4">
                        <button class="btn btn-light" style="color: black; font-weight: 400;">Login</button>
                    </div>
                    <div class="col-6">
                        <button class="btn btn-primary" style="width: 80px">Sign up</button>
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>