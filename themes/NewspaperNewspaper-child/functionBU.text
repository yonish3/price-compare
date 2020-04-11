<?php
// Exit if accessed directly
if ( !defined( 'ABSPATH' ) ) exit;

// BEGIN ENQUEUE PARENT ACTION
// AUTO GENERATED - Do not modify or remove comment markers above or below:

if ( !function_exists( 'chld_thm_cfg_locale_css' ) ):
    function chld_thm_cfg_locale_css( $uri ){
        if ( empty( $uri ) && is_rtl() && file_exists( get_template_directory() . '/rtl.css' ) )
            $uri = get_template_directory_uri() . '/rtl.css';
        return $uri;
    }
endif;
add_filter( 'locale_stylesheet_uri', 'chld_thm_cfg_locale_css' );

// END ENQUEUE PARENT ACTION

add_action('woocommerce_single_product_summary', 'my_test_fun');
// remove_action('woocommerce_single_variation', 'woocommerce_single_variation_add_to_cart_button', 20);
// add_filter( 'woocommerce_is_purchasable', '__return_false');

// remove_action('woocommerce_single_variation', 'woocommerce_single_variation', 10 );
remove_action( 'woocommerce_single_product_summary', 'woocommerce_template_single_excerpt', 20 );
add_filter( 'wc_product_sku_enabled', 'bbloomer_remove_product_page_sku' );

function bbloomer_remove_product_page_sku( $enabled ) {
    if ( ! is_admin() && is_product() ) {
        return false;
    }
    return $enabled;
}

add_action( 'woocommerce_single_product_summary', 'removing_variable_add_to_cart_template', 3 );
function removing_variable_add_to_cart_template(){
    global $product;

    // Only for variable products
    if( $product->is_type( 'variable' ) ){
        remove_action( 'woocommerce_single_product_summary', 'woocommerce_template_single_add_to_cart', 30 );
    }
}

function my_test_fun(){
    global $product;
    echo '<div class="tableContainer">
        <table>
        <thead>
        <!-- <tr>
            <th>First Name<th> 
            <th>Last Name<th> 
            <th>Last Name<th> 
        <tr> -->
        </thead>
        <tbody>
        <tr>
            <td><img class = "logoStyle" src="https://images-na.ssl-images-amazon.com/images/G/01/rainier/available_at_amazon_1200x600_Nvz5h2M.png" alt="Amazon Logo"></td> 
            <td>Starting At:</td> 
            <td>$';

    echo $product->get_price();

    echo '</td> 
            <td><button class = "btnSpecial btn">See deals</button></td> 
        </tr>
        <tr>
            <td><img class = "logoStyle" src="https://images-na.ssl-images-amazon.com/images/G/01/rainier/available_at_amazon_1200x600_Nvz5h2M.png" alt="Amazon Logo"></td> 
            <td>Starting At:</td> 
            <td>$';
            
    echo $product->get_price();
    
    echo '</td> 
            <td><button class = "btnSpecial btn">See deals</button></td> 
        </tr>
        </tbody>
        </table>
        </div>
    ';
    
}