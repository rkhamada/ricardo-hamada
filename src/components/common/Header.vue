<template>
    <head>
        <!-- Setup -->
        <title>{{ title }}</title>        
		<meta charset="utf-8" />
        <meta http-equiv="Content-Type" 
            content="text/html; charset=utf-8">
        <meta name="author"         :content="author">
        <meta name="keywords"       :content="keywords">
        <meta name="description"    :content="description">
        <meta name="viewport"       content="width=device-width, initial-scale=1.0">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="/styles/global.css" />

        <!-- Font Open Sans -->
        <link rel="preconnect" href="https://fonts.googleapis.com">
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
        <link href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,300;1,400;1,500;1,600;1,700;1,800&display=swap" rel="stylesheet"> 
        
        <!-- Favicon -->
        <link rel="apple-touch-icon" sizes="180x180" href="/favicon/apple-touch-icon.png">
        <link rel="icon" type="image/png" sizes="32x32" href="/favicon/favicon-32x32.png">
        <link rel="icon" type="image/png" sizes="16x16" href="/favicon/favicon-16x16.png">
        <link rel="manifest" href="/favicon/site.webmanifest">
        <link rel="mask-icon" href="/favicon/safari-pinned-tab.svg" color="#000000">
        <link rel="shortcut icon" href="/favicon/favicon.ico">
        <meta name="msapplication-TileColor" content="#000000">
        <meta name="msapplication-config" content="/favicon/browserconfig.xml">
        <meta name="theme-color" content="#ffffff">

        <slot />
    </head>
</template>

<script>

import { ref } from 'vue';

export default
{
    props: [ 'title', 'description', 'keywords', 'author' ],
    setup ( )
    { }
}

</script>