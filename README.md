# python3-input-password-with-asterisk
a simple way for inputting password with asterisk

Only works on Command.


        # -*- coding: utf-8 -*-
        import msvcrt
        def password_input():

            chars = []
            while True:
                char = msvcrt.getch().decode('utf8')
                if char == '\r' or char =='\n':
                    break
                elif char == '\b':
                    if len(chars) >= 1:
                        chars =  chars[:-1]
                        msvcrt.putch(b'\b')
                        msvcrt.putch(b'\x20') #\x20 means space
                        msvcrt.putch(b'\b')
                    else:
                        continue
                else:
                    if char != '\x00':
                        chars.append(char)
                        msvcrt.putch(b'*')
            return ''.join(chars)

        password = password_input()
        print('The password is:',password)
