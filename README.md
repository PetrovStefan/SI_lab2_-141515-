# SI_lab2_-141515-
Vtorata lab po mrezi

Odgovor na kodot za vtoroto prasanje (zakaceno na courses):

public boolean function (User user, List<String> allUsers) {
	//NODE 0 IS ENTRY IN FUNC
        String specialCharacters="!#$%&'()*+,-./:;<=>?@[]^_`{|}"; //NODE A
        if (user==null) {
            throw new RuntimeException("The user is not instantiated"); //NODE B
        }
        if (user.getUsername()==null || user.getPassword()==null)
            throw new RuntimeException("The user is missing some mandatory information"); //NODE C
        String password = user.getPassword(); //NODE D
        String passwordLower = password.toLowerCase(); //NODE E
        if (passwordLower.contains(user.getUsername().toLowerCase())) {
            return false; //NODE F
        }
        else if (passwordLower.length()<8)
            return false; //NODE G
        else {
            boolean digit = false, upper = false, special = false; //NODE H

            for (int i=0;i<password.length();i++) {
                if (Character.isDigit(password.charAt(i)))
                    digit = true; //NODE I
                if (Character.isUpperCase(password.charAt(i)))
                    upper = true; //NODE J
                if (specialCharacters.contains(String.valueOf(password.charAt(i))))
                    special = true; //NODE K
            }
            if (!digit || !upper || !special)
                return false; //NODE L
        }
        return true; //NODE M
    }
