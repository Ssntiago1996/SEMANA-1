# SEMANA-1/ Princinpal 1/main V1.C

/Librerias necesarias para hacer funcionar el programa
#include "freertos/FreeRTOS.h"
#include "freertos/task.h"
#include "driver/gpio.h"
#include "esp_timer.h"

#define PINLED1 32
#define MASKPINLED1 1ULL << PINLED1


//Función principal
void app_main(void)
{
    gpio_config_t configLed1 = {
        .pin_bit_mask = MASKPINLED1,
        .mode = GPIO_MODE_INPUT_OUTPUT,
        .pull_up_en = GPIO_PULLUP_DISABLE,
        .pull_down_en = GPIO_PULLDOWN_DISABLE
    };

    {
        gpio_set_level(PINLED1, 0);
        vTaskDelay(pdMS_TO_TICKS(500));
        gpio_set_level(PINLED1, 1);
        vTaskDelay(pdMS_TO_TICKS(500));

    }
    
}
