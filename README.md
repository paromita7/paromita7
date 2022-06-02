public class UpdateStudentField {
    
    public static List<Contact> studentEducation(){   
     
        //Get List of Students To load results to       
        List<Contact> studentList = new List<Contact>();
        //Get List of Students to run loop through
        List<Contact> studentToUpdate = new List<Contact>();
        
        for (Contact student:studentToUpdate){
            //Generate Random Value and link to qualification type
        	List<String> randomQualification = new List<String>{'Below Tertiary','Tertiary Graduate','Post Tertiary Graduate'};
        	Integer randomValue = randomQualification.size() -1;
        	Integer numberGenerated = Integer.valueof((Math.random()* randomValue));
        	String randomQualificationAssigned = randomQualification[numberGenerated];
                  
            student.Prior_Qualification__c = randomQualificationAssigned;//Assign a random qualification
            //Loop through Student and check Prior Qualification = 
            if(student.Prior_Qualification__c == 'Below Tertiary'){
                student.Enrolment_Progression__c = 'Advanced';
            }
            if(student.Prior_Qualification__c == 'Tertiary Graduate'){
                student.Enrolment_Progression__c = 'Ultimate';
            }
            if(student.Prior_Qualification__c == 'Post-Tertiary Graduate'){
                student.Enrolment_Progression__c = 'Extra';
            }
			studentList.add(student);            
        }              
        update studentList;
        return studentList;
    }

}
