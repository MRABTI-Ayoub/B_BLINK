################################################################################
# Automatically-generated file. Do not edit!
# Toolchain: GNU Tools for STM32 (12.3.rel1)
################################################################################

# Commandes de nettoyage
RM := rm -rf

# Inclusion des fichiers d'initialisation et de dépendances
-include ../makefile.init
-include sources.mk
-include objects.mk
-include ../makefile.defs

# Dépendances optionnelles
OPTIONAL_TOOL_DEPS := \
    $(wildcard ../makefile.defs) \
    $(wildcard ../makefile.init) \
    $(wildcard ../makefile.targets)

# Nom de l'artefact de build
BUILD_ARTIFACT_NAME := BLINKGIO14
BUILD_ARTIFACT_EXTENSION := elf
BUILD_ARTIFACT_PREFIX :=
BUILD_ARTIFACT := $(BUILD_ARTIFACT_PREFIX)$(BUILD_ARTIFACT_NAME)$(if $(BUILD_ARTIFACT_EXTENSION),.$(BUILD_ARTIFACT_EXTENSION),)

# Fichiers générés par les outils de build
EXECUTABLES += \
    BLINKGIO14.elf \

MAP_FILES += \
    BLINKGIO14.map \

SIZE_OUTPUT += \
    default.size.stdout \

OBJDUMP_LIST += \
    BLINKGIO14.list \

# Options du compilateur
CC := arm-none-eabi-gcc
CFLAGS := -mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -mfloat-abi=hard -mthumb
CFLAGS += -Wall -g -std=c11
CFLAGS += -specs=nosys.specs -specs=nano.specs
CFLAGS += -ffunction-sections -fdata-sections
CFLAGS += -DSTM32F429ZITX

# Options du linker
LD := $(CC)
LDFLAGS := -Wl,-Map=BLINKGIO14.map -Wl,--gc-sections
LDFLAGS := -Wl,-Map=BLINKGIO14.map -Wl,--gc-sections -T/home/ayoub/STM32CubeIDE/workspace_1.15.1/BLINKGIO14/STM32F429ZITX_FLASH.ld


# Répertoires des sources
SRCDIRS := Core/Src Core/Startup Drivers/STM32F4xx_HAL_Driver/Src

# Fichiers source
SRCS := $(wildcard $(addsuffix /*.c,$(SRCDIRS)))
OBJS := $(SRCS:.c=.o)

# Cible par défaut : construit l'exécutable ELF, le fichier binaire .bin et génère les sorties secondaires
all: main-build BLINKGIO14.bin

# Cible principale : construit l'exécutable ELF
main-build: $(BUILD_ARTIFACT) secondary-outputs

# Construction de l'exécutable ELF
$(BUILD_ARTIFACT): $(OBJS) $(USER_OBJS) $(LD_DEPS) $(OBJECTS)
	$(CC) $(CFLAGS) $(OBJS) $(USER_OBJS) $(LIBS) -o $(BUILD_ARTIFACT) $(LDFLAGS)
	@echo 'Finished building target: $@'
	@echo ' '

# Génération du fichier binaire .bin à partir de l'exécutable ELF
BLINKGIO14.bin: BLINKGIO14.elf
	arm-none-eabi-objcopy -O binary $< $@

# Génération des informations de taille
default.size.stdout: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-size  $(EXECUTABLES)
	@echo 'Finished building: $@'
	@echo ' '

# Génération du fichier de listage
BLINKGIO14.list: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objdump -h -S $(EXECUTABLES) > "BLINKGIO14.list"
	@echo 'Finished building: $@'
	@echo ' '

# Nettoyage des artefacts de build
clean:
	-$(RM) $(BUILD_ARTIFACT) $(MAP_FILES) $(SIZE_OUTPUT) $(OBJDUMP_LIST) BLINKGIO14.bin
	-@echo 'Cleaned up the project.'

# Cibles secondaires : gestion des sorties secondaires
secondary-outputs: $(SIZE_OUTPUT) $(OBJDUMP_LIST)

# Gestion des erreurs de configuration du linker
fail-specified-linker-script-missing:
	@echo 'Error: Cannot find the specified linker script. Check the linker settings in the build configuration.'
	@exit 2

# Avertissement en cas d'absence de script de lien spécifié
warn-no-linker-script-specified:
	@echo 'Warning: No linker script specified. Check the linker settings in the build configuration.'

# Déclaration des cibles comme phony (non fichier) pour éviter des conflits avec des fichiers du même nom
.PHONY: all clean dependents main-build fail-specified-linker-script-missing warn-no-linker-script-specified

# Inclusion des cibles spécifiques de l'utilisateur
-include ../makefile.targets

