# pdfMachineEncrypt

A Windows command line tool for encrypting a PDF file.

http://www.pdfmachine.com/genp/pdfmachine-command-line-tools.html

### USAGE

```
 pdfMachineEncrypt /f filename.pdf /p openpass /o ownerpass /accesability y|n /print y|n /change y|n /notes y|n /copy y|n /form y|n /assemble y|n
                where:
                f  - PDF filename, required: true
                help  - Help, required: false
                o  - Password to change the PDF security settings, required: false
                p  - Password to open the PDF for viewing, required: true
                accessability  - Security setting : Accessability, required: false
                assemble  - Security setting : document assembly, required: false
                change  - Security setting : change, required: false
                copy  - Security setting : Copy and extract, required: false
                form  - Security setting : Form fill or sign, required: false
                notes  - Security setting : add notes, required: false
                print  - Security setting : print, required: false

                e.g.
                pdfMachineEncrypt /f x.pdf /p mypass
                pdfMachineEncrypt /f x.pdf /p mypass /o someotherpass /print n /copy n
            
```



#pdfMachineStamp

A Windows command line tool for applying a text stamp or watermark to a PDF file.

### USAGE

```
            pdfMachineStamp /f filename.pdf /t "some text"
            parameters:
                 color  - Text color. Can be a name such as green, black, darkmagenta, cornflowerblue etc, or a RGB hex value such as #aabbcc
                     f  - PDF filename, required.
                  font  - Font name. Can be any Windows font.
                  help  - Help
               opacity  - Stamp opacity between 0 (transparent) and 1 (opaque)
                  page  - The page number to apply the stamp to. 0 means all pages.
                   pos  - Position: topleft, topcenter, topright, centerleft, center, centerright, bottomleft, bottomcenter, bottomright
                   rot  - Rotation in degrees
                  size  - Font size in points
                     t  - Stamp text, required.
                     x  - Position X in points. If 'pos' given is used as an offset.
                     y  - Position Y in points. If 'pos' given is used as an offset.

            e.g.
            pdfMachineStamp /f file.pdf /t "some text" /pos topcenter /color #fa0000
            pdfMachineStamp /f file.pdf /t "some text" /pos center /rot 45 /font "Brush Script MT" /size 50 /color green /opacity 0.5 /page 1
```



#pdfMachineSign

A Windows command line tool for digitally signing a PDF file using a certificate in the Windows certificate store.

### USAGE

```
            pdfMachineSign /f filename.pdf /sha1 thumbprint
            parameters:
                                 f  - PDF filename, required.
                              sha1  - SHA1 thumbprint identifying this certificate.  Use certmgr.msc to find, required.
                            reason  - Reason for signing.
                          location  - Location
                              page  - The page number to put the signature on.
                        image-file  - The image file. Can be JPEG, BMP, GIF.
                    show-cert-name  - Text appearance - show certficate name, y|n
                    show-dist-name  - Text appearance - show certficate distinguished name, y|n
                     show-location  - Text appearance - show location,  y|n
                       show-reason  - Text appearance - show reason, y|n
                    show-date-time  - Text appearance - show date time, y|n
                         show-date  - Text appearance - show date, y|n
                         show-time  - Text appearance - show time, y|n
                          position  - Valid values are: topleft, topright, bottomleft, bottomright, center, centerleft, centerright, centertop, centerbottom.
                                 x  - Horizontal position in points.  If 'position' is set, works as an offset.
                                 y  - Vertical position in points.  If 'position' is set, works as an offset.
                             width  - Width in points.
                            height  - Height in points.
                     timestamp-url  - URL of a RFC 3161 compliant timestamping server.
              certified-permission  - 0 - not certified (default), 1 - changes not allowed, 2 - changes to forms allowed, 3, - changes to annotations  allowed.
                              help  - Help
            e.g.
            pdfMachineSign /f file.pdf /sha1 aabbccddeeff00112233445566114455
            pdfMachineSign /f file.pdf /sha1 aabbccddeeff00112233445566114455 /image-file C:\sig\sig.jpg /date-time y /position bottomright /width 200 /height 100
```