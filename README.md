# JAVA_TEST_3
//Exam Code
package org.example;

import java.io.*;

public class PersonalDiary {

    public static void main(String[] args) {
        String fileName = "my_diary.txt";
        PersonalDiary diary = new PersonalDiary();
        diary.writeNote(fileName, "I started learning the java file.");
        diary.writeNote(fileName, "It was a bit confusing.");
        diary.writeNote(fileName, "I successfully created and copied a file!");
        System.out.println("Diary updated successfully!");
    }
    public void writeNote(String fileName, String note) {
        try {
            File file = new File(fileName);
            if (!file.exists()) {
                file.createNewFile();
            }
            FileWriter fw = new FileWriter(file, true);
            BufferedWriter bw = new BufferedWriter(fw);

            bw.write(note);
            bw.newLine();

            bw.close();
            fw.close();

        } catch (IOException e) {
            System.out.println("Error writing to file.");
            e.printStackTrace();
        }
    }
}
