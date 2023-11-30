class CSP:
    def __init__(self, variables, domains, constraints):
        self.variables = variables
        self.domains = domains
        self.constraints = constraints
def is_valid_assignment(var, value, assignment, constraints):
    for constraint in constraints:
        if var in constraint and value in assignment.get(constraint[0], []):
            return False
    return True
def backtracking_search(csp):
    return backtrack({}, csp)
def backtrack(assignment, csp):
    if len(assignment) == len(csp.variables):
        return assignment
    var = select_unassigned_variable(assignment, csp)
    for value in order_domain_values(var, assignment, csp):
        if is_valid_assignment(var, value, assignment, csp.constraints):
            assignment[var] = value
            result = backtrack(assignment, csp)
            if result is not None:
                return result
            del assignment[var]
    return None
def select_unassigned_variable(assignment, csp):
    for var in csp.variables:
        if var not in assignment:
            return var
def order_domain_values(var, assignment, csp):
    return csp.domains[var]
variables = ['WA', 'NT', 'SA', 'Q', 'NSW', 'V', 'T']
domains = {
    'WA': ['R', 'G', 'B'],
    'NT': ['R', 'G', 'B'],
    'SA': ['R', 'G', 'B'],
    'Q': ['R', 'G', 'B'],
    'NSW': ['R', 'G', 'B'],
    'V': ['R', 'G', 'B'],
    'T': ['R', 'G', 'B']
}
constraints = [
    ('WA', 'NT'), ('WA', 'SA'), ('NT', 'SA'),
    ('NT', 'Q'), ('SA', 'Q'),
    ('SA', 'NSW'), ('SA', 'V'),
    ('NSW', 'Q'), ('NSW', 'V'),
    ('Q', 'T'), ('V', 'T')]
csp = CSP(variables, domains, constraints)
result = backtracking_search(csp)
if result is not None:
    print("Solution found:",domains)
    print(result)
else:
    print("No solution exists.")
