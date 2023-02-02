VENDOR=Gigabyte
PROJECT_NAME=ga-h97n-ami-flashrom
VERSION=F5

FIRMWARE_FILES=				\
	H97N.F5
METAINFO_FILES=				\
	GA-G97N.ami-flashrom.metainfo.xml

all: $(VENDOR)-$(PROJECT_NAME)-$(VERSION).cab

clean:
	rm *.cab

check: $(METAINFO_FILES)
	appstream-util validate-relax $(METAINFO_FILES)

H97N.F5:
    wget https://download.gigabyte.com/FileList/BIOS/mb_bios_ga-h97n_f5.zip
    unzip mb_bios_ga-h97n_f5.zip H97N.F5
    rm mb_bios_ga-h97n_f5.zip

%.cab: $(FIRMWARE_FILES) $(METAINFO_FILES)
	gcab --create --nopath $@ $(FIRMWARE_FILES) $(METAINFO_FILES)
