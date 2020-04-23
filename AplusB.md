# A + B

From [Rosetta Code](http://rosettacode.org/wiki/A%2BB):

> A+B   ─── a classic problem in programming contests,   it's given so contestants can gain familiarity with the online judging system being used.
>
> **Task**
> Given two integers,   A and B.
> 
> Their sum needs to be calculated.
>
> **Input data**
> Two integers are written in the input stream, separated by space(s):
>
> (−1000≤A,B≤+1000)
>
> **Output data**
> The required output is one integer:   the sum of A and B.
>
> **Example**
> input  	output  
> 2 2	4
> 3 2	5

## Discussion:
This is an incredibly simple problem that essentially amounts to a single expression in most programming languages. Writing a function that accomplishes this may seem like overkill, given that such functions are native in most languages, but we are doing it here to demonstrate the format we are using, which is meant to practice both "functional programming" and "test-driven development."

## Pseudo-Code:

	expect add(2, 2) tobe 4 // case with two identical inputs, both positive
	expect add(3, 2) tobe 5 // case with two different inputs, both positive
	expect add(-3, 2) tobe -1 // case with two different inputs, one positive and one negative
	expect add(-1000, 1000) tobe 0 // case with extremes cancelling out
	expect add(10, 0) tobe 10 // case of adding zero
	expect add(0, 0) tobe 0 // case of adding zero to itself
	expect add(-1000, 10) tobe -990 // another case at the extreme margin
	
	define add(A, B) as:
		return: A + B

## Haskell:

Unit Tests (HUnit):

Function Code:


## Python:

Unit Tests (using PyUnit):
	Class TestAddition(unittest.test-case):
		def AddPosIdentical(self):
			self.assertEquals(add(2,2),4)
		def AddPosDifferent(self):
			self.assertEquals(add(3,2),5)
		def AddMixDifferent(self):
			self.assertEquals(add(-3,2),-1)
		def AddExtrCancels(self):
			self.assertEquals(add(-1000,1000),0)
		def AddZero(self):
			self.assertEquals(add(10,0),10)
		def AddZeroToZero(self):
			self.assertEquals(add(0,0),0)
		def AddExtremeNeg(self):
			self.assertEquals(add(-1000,10),-990)
	
	if __name__ == '__main__':
		unittest.main()

Function Code:
	def add(A, B):
		return A + B

## PHP

Unit Tests (PHPUnit):
	class AdditionTest extends TestCase
	{
		/**
		* @dataProvider additionProvider
		*/
		public function testAdd($a, $b, $expected) 
		{
			this->assertSame($expected, $a + $b);
		}
		
		public function additionProvider()
		{
			return [
				[2, 2, 4],
				[3, 2, 5],
				[-3, 2, -1],
				[-1000, 1000, 0],
				[10, 0, 10],
				[0, 0, 0],
				[-1000, 10, -990]
			];
		}
	}

Function Code:
	public function add($a, $b)
	{
		return $a + $b;
	}

## TypeScript

Unit Tests (Jest):

	test.each([[2,2,4],[3,2,5],[-3,2,-1],[-1000,1000,0],[10,0,10],[0,0,0],[-1000,10,-990]])(
		'adding %i to %i returns %i',
		(a, b, expected) => {
			expect(a + b).toBe(expected);
		},
	);

Function Code:
	function add(a :int, b :int) {
		return a + b;
	}

## Shell

Unit Tests (Bats):
	@test "2 + 2" {
		$result="$(add 2 2)"
		["$result" -eq 4]
	}
	@test "3 + 2" {
		$result="$(add 3 2)"
		["$result" -eq 5]
	}
	@test "-3 + 2" {
		$result="$(add -3 2)"
		["$result" -eq -1]
	}
	@test "-1000 + 1000" {
		$result="$(add -1000 1000)"
		["$result" -eq 0]
	}
	@test "10 + 0" {
		$result="$(add 10 0)"
		["$result" -eq 10]
	}
	@test "0 + 0" {
		$result="$(add 0 0)"
		["$result" -eq 0]
	}
	@test "-1000 + 10" {
		$result="$(add -1000 10)"
		["$result" -eq -990]
	}

Function Code:
	add() {
		return $1 + $2
	}

## SQL

Unit Tests:


Function Code: