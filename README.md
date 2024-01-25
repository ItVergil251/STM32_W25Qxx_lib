# STM32_W25Qxx_lib

## Як підключити бібліотеку у PlatformIO

У `Core/Inc/main.h` сконфігуруйте бібліотеку додавши 

    /* Exported types ------------------------------------------------------------*/
    /* USER CODE BEGIN ET */
    extern SPI_HandleTypeDef hspi3; // пропишіть ваш SPI який використовуєте
    extern UART_HandleTypeDef huart2; // пропишіть ваш UART який використовуєте
    /* USER CODE END ET */

    /* Exported constants --------------------------------------------------------*/
    /* USER CODE BEGIN EC */
    // Прописуємо порти і піни які ви кикористовуєте для СS піна
    #define cs_set() HAL_GPIO_WritePin(SPI3_CS_GPIO_Port, SPI3_CS_Pin, GPIO_PIN_RESET)
    #define cs_reset() HAL_GPIO_WritePin(SPI3_CS_GPIO_Port, SPI3_CS_Pin, GPIO_PIN_SET)
    /* USER CODE END EC */