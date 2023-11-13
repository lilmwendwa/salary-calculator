# salary-calculator

class PayrollCalculator:
    def __init__(self):
        self.employee_name = "YourRegistrationNumber"
        self.rate_per_hour = 0.0
        self.hours_per_day = 0.0
        self.days_worked = 0

    def get_user_input(self):
        self.employee_name = input("Enter employee's name (Registration Number): ")
        self.rate_per_hour = float(input("Enter rate per hour: "))
        self.hours_per_day = float(input("Enter hours per day: "))
        self.days_worked = int(input("Enter number of days worked: "))

    def calculate_salary(self):
        gross_salary = self.rate_per_hour * self.hours_per_day * self.days_worked
        tax_deduction = 0.15 * gross_salary
        philhealth_deduction = 0.05 * gross_salary
        sss_deduction = 0.02 * gross_salary
        net_salary = gross_salary - tax_deduction - philhealth_deduction - sss_deduction

        return gross_salary, net_salary

    def display_salary(self, gross_salary, net_salary):
        print("\nPayroll Summary for", self.employee_name)
        print("Rate per hour: $", self.rate_per_hour)
        print("Hours per day: ", self.hours_per_day)
        print("Days worked: ", self.days_worked)
        print("Gross Salary: $", gross_salary)
        print("Tax (15%): $", 0.15 * gross_salary)
        print("Philhealth (5%): $", 0.05 * gross_salary)
        print("SSS (2%): $", 0.02 * gross_salary)
        print("Net Salary: $", net_salary)

if __name__ == "__main__":
    payroll_calculator = PayrollCalculator()
    payroll_calculator.get_user_input()
    gross_salary, net_salary = payroll_calculator.calculate_salary()
    payroll_calculator.display_salary(gross_salary, net_salary)
