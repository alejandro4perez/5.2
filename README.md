#5.2


/**
 *
 * 
 * Priority
**/
public interface Priority
{
   public void setPriority(int priority);
   public int getPriority();
}


/**
 * 
 * 
 * Task
**/
public class Task 
{
   private String task,due;
   private int priorityLevel;
   //-----------------------------------------------------------------
   //  Sets up the question with a default complexity.
   //-----------------------------------------------------------------
   public Task(String assignment)
   {
      task = assignment;
      priorityLevel = 1;
   }
   //-----------------------------------------------------------------
   //  Sets the priority level.
   //-----------------------------------------------------------------
   public void setPriority(int level)
   {
      priorityLevel = level;
   }
   //-----------------------------------------------------------------
   //  Returns the complexity level for this question.
   //-----------------------------------------------------------------
   public int getPriority()
   {
      return priorityLevel;
    }
   //-----------------------------------------------------------------
   //  Returns the task.
   //-----------------------------------------------------------------
   public String getTask()
   {
      return task;
    }
   //-----------------------------------------------------------------
   //  Returns the answer to this question.
   //-----------------------------------------------------------------
   public String getDue()
   {
      return due;
   }
   //-----------------------------------------------------------------
   //  Returns true if the candidate answer matches the answer.
   //-----------------------------------------------------------------
   public boolean dueCorrect (String candidateDue)
   {
      return due.equals(candidateDue);
   }
   
   public int compareTo(Object obj)
   {
       int otherPriorityLevel = ((Task)obj).getPriority();
       int n;
       if(priorityLevel < otherPriorityLevel)
            n = 1;
       else if(priorityLevel > otherPriorityLevel)
            n = -1;
       else
            n = 0;
       
       return n;
   }
   //-----------------------------------------------------------------
   //  Returns this question (and its answer) as a string.
   //-----------------------------------------------------------------
   public String toString()
   {
      return task;
   }
}


/**
 * 
 * 
 * Driver
**/
public class Driver
{
   public static void main(String[] args)
   {
       Task t1, t2;
       
       t1 = new Task("Wake Up”);
       t1.setPriority(1);
       t2 = new Task("Eat");
       t2.setPriority(2);
       
       System.out.print(t1.getTask());
       System.out.println("(" + t1.getPriority() + "st)");
       System.out.println();
       System.out.print(t2.getTask());
       System.out.println("(" + t2.getPriority() + "nd)");
       
       if(t1.compareTo(t2) == 1)
           System.out.println(t1 + " is first.");
       else
            System.out.println(t2 + " is second.");
            
       if(t1.compareTo(t2) == -1)
           System.out.println(t1 + " is first.");
       else
            System.out.println(t2 + " is second.");
   }
}
